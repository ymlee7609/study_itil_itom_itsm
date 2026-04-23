# Event vs Alert vs Incident

모니터링에서 인시던트로 이어지는 **3단계 체인**. "알람 떴어요"라는 말 속에 이 셋이 섞인다. ITOM과 ITSM의 경계를 이해하는 핵심.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 발생 체인](#2-발생-체인)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Event (이벤트) | Alert (알람) | Incident (인시던트) |
|------|---------------|-------------|---------------------|
| **정의** | CI/서비스 상태의 **감지된 변화** | **주의가 필요한** 이벤트 | 서비스의 **계획되지 않은 중단 또는 저하** |
| **주체 판단** | 시스템 자동 생성 (가치 중립) | 규칙/임계값에 의한 분류 | 서비스·사용자 영향 확인 |
| **영향도** | 있을 수도, 없을 수도 | 조치가 필요할 수 있음 | 실제 영향 존재 |
| **관리 프로세스** | Monitoring / Event Management | Event → Alert 분류 | Incident Management |
| **담당 시스템** | Datadog, Zabbix, Splunk (수집) | AlertManager, PagerDuty (알림) | ServiceNow, Jira SM (티켓) |
| **통계적 비율** | 수천만 건/일 | 수백 건/일 | 수십 건/일 |

---

## 2. 발생 체인

```
 로그/메트릭 발생          규칙·임계값 평가             영향 확인
       │                         │                         │
       ▼                         ▼                         ▼
  ┌────────┐   필터링        ┌──────┐   영향 발생      ┌──────────┐
  │ Event  │ ─────────────► │Alert │ ─────────────► │ Incident │
  └────────┘                └──────┘                 └──────────┘
     많음                   선별됨                   실제 영향
  (100% 수집)              (~0.1%)                  (~0.01%)

  ITOM 영역                                         ITSM 영역
  (Monitoring)                                      (Service Desk)
```

- **Event**: 원시 데이터. 로그 라인, 메트릭 포인트, 상태 변경
- **Alert**: 주의 필요. 규칙에 의해 분류(Informational/Warning/Error/Critical)
- **Incident**: 서비스 영향 확인 → 티켓 생성

**Alert ≠ Incident**: 모든 Alert이 Incident는 아니다. False positive, 자동 복구 이벤트 등은 Incident로 전환 안 됨.

---

## 3. 실무 예시

### 예시 1: 디스크 사용률

| 단계 | 내용 |
|------|------|
| **Event** | 서버 디스크 사용률 메트릭 매 1분 수집 (70%, 72%, 80%, 92%...) |
| **Alert** | 임계값 90% 초과 → Warning Alert 발송 ("disk-usage-warning") |
| **조치 불요** | 자동 로그 정리 스크립트로 85%로 복구 → Alert 해제, Incident 생성 안 함 |
| **또는** | 계속 92% 유지 + 서비스 응답 지연 → **Incident 생성** ("결제 응답 3초 초과") |

### 예시 2: 로그인 실패

| 단계 | 내용 |
|------|------|
| **Event** | 로그인 실패 로그 이벤트 초당 10건 |
| **Alert** | 평소 대비 5배 증가 → 의심 Alert |
| **Incident 전환** | 실제 사용자 "로그인 안 돼요" 접수 다수 → Incident |
| **Incident 불전환** | 브루트포스 공격으로 판정 → Security Event로 분기 (차단) |

### 예시 3: 노이즈 관리

| 지표 | 건수 |
|------|------|
| 일일 Event | 1,200만 건 |
| 임계값 초과 Alert | 800건 |
| 사람 개입 필요한 Alert | 60건 |
| Incident 생성 | 12건 |
| 실제 SLA 영향 Incident | 3건 |

→ 이벤트의 **0.000025%만 실제 SLA 영향**. 필터링 전략이 운영팀의 수면을 결정.

---

## 4. 왜 이 구분이 중요한가

### (1) Alert Fatigue (알람 피로) 방지

- 모든 Event를 Alert으로 올리면 **알람 1,200만 건/일** → 아무도 안 봄
- Alert을 Incident로 자동 전환하면 **노이즈가 ITSM까지 오염**
- ITOM 레벨에서 충분히 걸러야 ITSM이 정상 작동

### (2) 자동화 경계 설정

| 단계 | 자동화 가능성 |
|------|--------------|
| Event → Alert | **완전 자동** (규칙/ML) |
| Alert → 자동 복구 | **부분 자동** (Runbook, Self-healing) |
| Alert → Incident | **판단 필요** (영향 평가 후) |

### (3) 도구 체계의 분리

- ITOM 도구 (Datadog, Zabbix, Prometheus): Event 수집, Alert 발송
- 통합 알림 (PagerDuty, Opsgenie): Alert 라우팅, 에스컬레이션
- ITSM 도구 (ServiceNow, Jira): Incident 티켓, SLA 관리

→ 3개 도구 층이 **역할 혼선 없이 연동**되어야 체인이 흐름.

### (4) KPI 측정의 의미 차이

| 지표 | 무엇을 의미 |
|------|------------|
| Event 수 | 시스템 활성도 (의미 낮음) |
| Alert 수 / False Positive 비율 | 모니터링 품질 |
| Alert → Incident 전환율 | 필터링 품질 |
| Incident 수 / MTTR | 서비스 안정성 |

### (5) AIOps의 핵심 공략 지점

ITIL 5와 AIOps는 **Event → Alert → Incident 체인 자동화**를 목표로 함:
- Noise Reduction: 유사 Event 묶기
- Root Cause Analysis: 수천 Alert 중 원인 1개 찾기
- Auto-remediation: Alert에서 자동 복구 후 Incident 미생성

---

## 5. 한눈 정리

```
     ITOM 영역                          ITSM 영역
───────────────                      ───────────────

Event → Alert → [자동 복구 or Incident 전환]
  │       │              │
수집     필터링         판단
많음     선별           영향 확인
Zabbix   PagerDuty     ServiceNow
```

---

## 한 줄 요약

**Event는 감지된 변화, Alert은 주의 필요한 이벤트, Incident는 서비스 영향이 확인된 티켓.** ITOM이 Event/Alert을 다루고 ITSM이 Incident를 다룬다. 체인 중 어느 단계에서 필터링하느냐가 운영 품질을 결정한다.

---

## 관련 문서

- [Incident vs Problem vs Known Error](incident_vs_problem_vs_known_error.md)
- [Service Request vs Incident](service_request_vs_incident.md)
- [ITOM 핵심 역량](../itom/03-capabilities.md)
- [ITOM AIOps 트렌드](../itom/05-aiops-trends.md)
