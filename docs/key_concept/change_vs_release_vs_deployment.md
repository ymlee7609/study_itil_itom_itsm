# Change vs Release vs Deployment

"변경했다/배포했다/릴리즈했다"를 모두 한 뜻으로 쓰는 것이 흔한 오용. ITIL은 이 3단계를 **명확히 분리**하며, 각 단계마다 담당자·승인 체계·실패 시 롤백 책임이 다르다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 생애주기 흐름](#2-생애주기-흐름)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Change (변경) | Release (릴리즈) | Deployment (배포) |
|------|--------------|------------------|------------------|
| **정의** | 서비스/구성요소에 대한 **추가·수정·제거** 결정 | **하나 이상의 변경을 묶어** 운영환경으로 이전할 준비 | 구성요소를 **실제 환경에 설치/활성화**하는 행위 |
| **질문** | "무엇을 왜 바꿀까?" | "무엇을 언제 묶어서 내보낼까?" | "어떻게 실제로 올릴까?" |
| **산출물** | RFC, Change Record | Release Package | Live 환경의 동작 |
| **담당 프랙티스** | Change Enablement | Release Management | Deployment Management |
| **결정 권한** | CAB, Change Authority | Release Manager | 운영팀, SRE, DevOps |
| **DevOps 매핑** | 티켓/승인 | 버전 태그, CI 파이프라인 | CD, kubectl apply, helm upgrade |

---

## 2. 생애주기 흐름

```
┌─────────┐     ┌─────────┐     ┌────────────┐
│ Change  │ ──► │ Release │ ──► │ Deployment │
│ (What?) │     │ (When?) │     │ (How?)     │
└─────────┘     └─────────┘     └────────────┘
  RFC 승인        Release 1.2     kubectl apply
  (결정)          Package 생성    (실행)
                  (패키징)
```

**핵심**: Change는 **결정**, Release는 **패키징·일정**, Deployment는 **실행**이다.

- Change 없이 Deployment는 불가 (무단 변경)
- Release 없이 Deployment는 가능 (긴급 Hotfix 패치) — 단 추적 필수
- 한 Release에 여러 Change, 한 Change가 여러 Deployment (Dev→Stg→Prod)로 분할될 수 있음

---

## 3. 실무 예시

### 예시 1: CRM v2.3 업그레이드

| 단계 | 구분 | 내용 |
|------|------|------|
| 1 | **Change** | RFC-2026-045: "CRM v2.3으로 업그레이드 (고객 리포트 기능 추가)" → CAB 승인 |
| 2 | **Release** | Release 2.3.0 패키지 = v2.3 빌드 + DB 마이그레이션 스크립트 + 사용자 교육 자료 묶음 |
| 3 | **Deployment** | Dev 배포 → QA → Stg → Prod 단계적 배포 (3일에 걸쳐 실행) |

### 예시 2: 긴급 보안 패치

| 단계 | 구분 | 내용 |
|------|------|------|
| 1 | **Emergency Change** | Log4Shell CVE 대응 긴급 변경 → eCAB 신속 승인 |
| 2 | **(Release 생략)** | 패키징 단계 우회, 핫픽스 직행 |
| 3 | **Deployment** | 모든 서버에 즉시 배포 (사후 Release 기록 보완) |

### 예시 3: 한 Release에 여러 Change

| 항목 | 내용 |
|------|------|
| **Release 3.1.0** | 월간 정기 릴리즈 |
| Change 묶음 | RFC-101 (로그인 개선) + RFC-102 (UI 버그) + RFC-103 (API 추가) |
| Deployment | 일요일 02:00 일괄 배포 |

---

## 4. 왜 이 구분이 중요한가

### (1) 승인과 실행의 분리 = 통제 가능성

- 실행자(Deployment)가 결정권자(Change)를 겸하면 **부정 변경** 통제 불능
- 감사(SOX, ISMS) 대응 시 "누가 승인했고, 무엇을 묶었고, 누가 실제 올렸나"를 분리 추적해야 함

### (2) 실패 시 책임 소재 명확화

| 실패 유형 | 책임 |
|----------|------|
| 잘못된 변경 결정 | Change Authority (의사결정 오류) |
| 잘못된 번들링 | Release Manager (호환성 누락) |
| 잘못된 실행 | Deployer (롤백 절차 미준수) |

### (3) DevOps/CD 시대에도 사라지지 않음

"CI/CD로 자동화했으니 Change 프로세스 필요 없다"는 오해가 많음. 현실:
- **Standard Change** (사전 승인된 변경 유형)로 자동 처리 가능 → 그러나 **기록은 남아야** 함
- Change = 무엇을 / Release = 버전 태그 / Deployment = 파이프라인 실행 — **세 층이 DevOps에도 그대로 존재**

### (4) 배포 실패 ≠ 변경 실패

- **Deployment 롤백**: 이전 버전으로 복구 (기술적)
- **Change 철회**: 결정 자체를 되돌림 (비즈니스·계약적)
- Deployment만 롤백하고 Change가 "완료"로 남아 있으면 기록 불일치 발생

---

## 5. 한눈 정리

```
Change                Release                Deployment
(결정)                (묶음)                  (실행)
─────                ───────                 ──────────
"왜/무엇을"          "언제/무엇과 함께"       "어떻게/어디에"
CAB 승인             Release Package          kubectl / ansible
RFC 티켓             버전 태그 v1.2.3          Live 환경 반영
Change Authority     Release Manager          SRE/운영팀
```

---

## 한 줄 요약

**Change는 결정, Release는 패키징, Deployment는 실행.** 하나로 섞으면 승인·감사·롤백이 전부 무너진다. DevOps 시대에도 세 개념은 자동화 아래 살아 있다.

---

## 관련 문서

- [ITIL 4 핵심 프로세스 심화](../itil4/09-key-processes.md)
- [ITIL 4 서비스 관리 프랙티스](../itil4/07-practices-service.md)
- [Incident vs Problem vs Known Error](incident_vs_problem_vs_known_error.md)
