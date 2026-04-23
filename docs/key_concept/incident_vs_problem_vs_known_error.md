# Incident vs Problem vs Known Error

ITIL 실무에서 **가장 자주 혼용**되는 3개 용어. "장애 났어요"라는 한마디 속에 이 셋이 뒤섞여 있다. 구분하지 못하면 인시던트 관리와 문제 관리가 한 프로세스로 엉킨다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 생애주기 흐름](#2-생애주기-흐름)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Incident (인시던트) | Problem (문제) | Known Error (알려진 오류) |
|------|--------------------|---------------|-------------------------|
| **정의** | 서비스의 **계획되지 않은 중단** 또는 품질 저하 | **하나 이상의 인시던트의 원인** (또는 잠재적 원인) | **원인이 분석되었고 임시조치가 있는** 문제 |
| **관심사** | "빨리 복구" (Restore) | "왜 일어났나" (Root cause) | "재발 시 어떻게 대응" (Workaround 문서화) |
| **담당 프로세스** | Incident Management | Problem Management | Problem Management (하위 상태) |
| **시간 축** | 즉시 (수분~수시간) | 중장기 (수일~수주) | 영구 (해결 또는 수용될 때까지) |
| **목표** | 서비스 복구 | 반복 차단 | 재발 시 신속 대응 |

---

## 2. 생애주기 흐름

```
 사용자가 영향 체감                원인 분석 착수              원인 + 임시조치 확정
       │                              │                            │
       ▼                              ▼                            ▼
  ┌─────────┐    반복 발견        ┌────────┐    분석 완료       ┌───────────┐
  │Incident │ ────────────────► │Problem │ ─────────────────► │Known Error│
  └─────────┘                    └────────┘                    └───────────┘
       │                              │                            │
  빠른 복구                       근본 원인 제거                  영구 해결(Fix)
  (Workaround 적용)              (Change 발행)                  또는 Accept
```

- **Incident 발생** → 서비스 복구가 1순위
- **Incident 반복** 또는 중대성 → **Problem**으로 승격 (원인 추적 시작)
- **원인+임시조치 확보** → **Known Error**로 전환 (KEDB 등록)
- **근본 해결** → Change 프로세스를 통해 수정 배포 → Problem 종결

---

## 3. 실무 예시

### 예시 1: 이메일 시스템 장애

| 단계 | 용어 | 상황 |
|------|------|------|
| 1 | **Incident #1** | 월요일 오전 "메일이 안 보내져요" 티켓 50건 접수 → 서비스 복구(서버 재시작)로 종결 |
| 2 | **Incident #2** | 수요일 동일 현상 재발 → 재시작으로 복구 |
| 3 | **Problem 등록** | 반복 패턴 발견 → Problem 티켓 생성, 원인 조사 착수 |
| 4 | **Known Error** | SMTP 큐 오버플로우 원인 확인 + 임시조치(큐 크기 임계값 경보) 확립 → KEDB 등록 |
| 5 | **Fix (RFC)** | SMTP 큐 사이즈 증설 변경 요청 → Change 승인 → 배포 → Problem 종결 |

### 예시 2: 결제 API 오류

| 시점 | 용어 | 내용 |
|------|------|------|
| 10:00 | Incident | "결제 실패 500 오류" — SRE가 Pod 재배포로 복구 |
| 10:30 | Incident 추가 3건 | 동일 오류 반복 |
| 11:00 | Problem 승격 | 메모리 누수 의심, 조사 착수 |
| 14:00 | Known Error | 특정 라이브러리 leak 확인, 1시간마다 재시작(크론)으로 workaround |
| D+3 | Resolved | 라이브러리 패치 적용 |

---

## 4. 왜 이 구분이 중요한가

### (1) KPI가 완전히 다르다

| 프로세스 | 핵심 KPI |
|---------|---------|
| Incident Management | **MTTR**, 1차 해결율, SLA 준수율 |
| Problem Management | **재발률 감소**, Known Error DB 활용률, 근본 해결 건수 |

→ Incident만 잡으면 "빨리 복구"만 잘하는 소방수 조직이 됨. Problem을 병행해야 **불나는 구조 자체**가 줄어든다.

### (2) 조직 역할이 다르다

- **Incident**: 서비스 데스크 + L1/L2 (속도)
- **Problem**: 전문 분석가 + 아키텍트 (깊이)
- 동일 인력이 동시 수행 시 → 속도·깊이 둘 다 실패

### (3) ServiceNow/Jira 등 도구에서 별도 모듈

실무 도구는 Incident Table과 Problem Table을 분리한다. 한 티켓에 둘을 섞으면 리포팅·자동화가 전부 깨진다.

### (4) Known Error ≠ "해결된 문제"

Known Error는 **"원인은 알지만 아직 근본 해결 안 된 상태"**. 재발 시 Workaround로 신속 대응하기 위한 상태이지, 종결 상태가 아니다.

---

## 5. 한눈 정리

```
증상 층          원인 층              대응 지식 층
─────           ─────               ─────────
Incident ───► Problem ───► Known Error ───► Resolved
"서비스 중단"  "왜 일어났나"    "어떻게 대응"    "영구 해결"
속도 중심     깊이 중심         지식 중심       변화 관리
```

---

## 한 줄 요약

**Incident는 증상, Problem은 원인, Known Error는 원인+임시조치가 있는 상태.** Incident는 복구, Problem은 재발 차단, Known Error는 재발 시 신속 대응을 목표로 한다.

---

## 관련 문서

- [ITIL 4 핵심 프로세스 심화](../itil4/09-key-processes.md)
- [Service Request vs Incident](service_request_vs_incident.md)
- [Workaround vs Fix vs Resolution](workaround_vs_fix_vs_resolution.md)
- [Event vs Alert vs Incident](event_vs_alert_vs_incident.md)
