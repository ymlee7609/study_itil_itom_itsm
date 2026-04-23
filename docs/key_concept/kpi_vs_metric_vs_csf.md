# KPI vs Metric vs CSF vs Measurement

"지표가 너무 많다"는 조직의 공통 고민. 문제는 지표 수가 아니라 **층위가 섞여 있다는 것**. CSF → KPI → Metric → Measurement 위계를 이해해야 한다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 계층 관계](#2-계층-관계)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | 풀네임 | 정의 | 층위 |
|------|--------|------|------|
| **CSF** | Critical Success Factor | 목표 달성에 **필수적으로 성공**해야 할 요인 | 최상위 (전략) |
| **KPI** | Key Performance Indicator | CSF 달성 여부를 **판단**하는 핵심 지표 | 중위 (성과) |
| **Metric** | Metric (지표) | 정량적으로 측정된 **모든 수치** | 하위 (측정값) |
| **Measurement** | Measurement (측정) | 특정 시점의 **개별 관측 값** | 원시 데이터 |

---

## 2. 계층 관계

```
   Goal (목표)           "서비스 품질 향상"
     │
     ▼
   CSF (성공 요인)       "신속한 장애 대응"
     │                   "사용자 만족도 확보"
     ▼
   KPI (핵심 지표)       "MTTR < 1시간"
     │                   "CSAT ≥ 4.5/5"
     ▼
   Metric (지표)         "인시던트 해결 시간"
     │                   "설문 응답 점수"
     ▼
   Measurement (관측)    "티켓 #1234 = 47분"
                         "사용자 김○○ = 5점"
```

- **Goal**: 왜 (전략적 방향)
- **CSF**: 무엇을 (핵심 요인 — 정성적일 수 있음)
- **KPI**: 얼마나 (측정 가능한 성공 기준)
- **Metric**: 어떻게 (측정 방법/수치)
- **Measurement**: 각 데이터 포인트

---

## 3. 실무 예시

### 예시 1: 서비스 데스크

| 층위 | 항목 |
|------|------|
| **Goal** | 사용자 생산성 최대화 |
| **CSF** | 신속한 1차 해결 / 편리한 접근성 / 정확한 정보 제공 |
| **KPI** | FCR ≥ 75%, 평균 응답시간 < 1분, 재문의율 < 10% |
| **Metric** | 1차 해결 건수 / 총 접수 건수, 채팅 첫 응답 소요초, 재문의 티켓 수 |
| **Measurement** | "2026-04-23 FCR = 78.4%", "평균 응답 52초" |

### 예시 2: 변경 관리

| 층위 | 항목 |
|------|------|
| Goal | 변경으로 인한 서비스 중단 최소화 |
| CSF | 철저한 영향 평가 / 롤백 준비 |
| KPI | Change Success Rate ≥ 95%, Emergency Change 비율 ≤ 5% |
| Metric | 실패 Change 수 / 전체 Change 수 |
| Measurement | "RFC-2026-045 = 성공" |

### 예시 3: 흔한 오용

| 잘못된 표현 | 문제 | 올바른 표현 |
|------------|------|-----------|
| "MTTR 지표(Metric)를 관리해요" | 관리 의미 불명확 | "MTTR을 **KPI로** 관리" (성공 여부 판단) |
| "KPI 50개로 관리" | KPI 인플레이션 (사실상 Metric 모음) | "KPI 5개 + Supporting Metric 45개" |
| "CSAT 수치가 낮아요" | 층위 불명확 | "CSAT **KPI**가 **목표치 미달**" |

---

## 4. 왜 이 구분이 중요한가

### (1) "KPI 인플레이션" 방지

- 많은 조직이 50~100개 "KPI"를 갖고 있음 → 실제로는 Metric 모음
- KPI는 보통 **5~15개**가 적정 (부서별·서비스별)
- 나머지는 **Supporting Metric**으로 분류

### (2) 대시보드 설계 원칙

| 대상 | 보여줄 층위 |
|------|------------|
| 경영진 | Goal + CSF + **KPI 요약** |
| 서비스 매니저 | KPI + **Supporting Metric** |
| 운영 실무자 | Metric + **Measurement** |

→ 임원에게 Measurement 수준을 보여주면 "그래서 뭐가 문제냐"가 됨.

### (3) Lead vs Lag Indicator

KPI는 시간 성격에 따라:
- **Lag KPI** (결과 지표): MTTR, CSAT, SLA 준수율 → 사후 측정
- **Lead KPI** (선행 지표): Change 영향평가 완료율, 모니터링 커버리지 → 사전 예측

→ Lag만 보면 "버스 놓치고 달린" 뒤 대응. Lead를 함께 봐야 **예방** 가능.

### (4) ITIL 4의 "Start where you are" 원칙과 연결

- 현재 측정 중인 Metric 목록 작성
- 상위 CSF·KPI로 그룹핑
- 누락된 KPI 식별, 불필요한 Metric 제거
- **Goal에 연결되지 않는 Metric은 수집 중단**

### (5) Balanced Scorecard와의 호환

BSC 4개 관점 (Financial, Customer, Internal Process, Learning & Growth) 각각에 CSF → KPI → Metric 구조 적용 가능.

### (6) 숫자의 함정

- "MTTR 30분"만 보면 좋은 KPI처럼 보임
- 그러나 **CSF**(신속 대응)가 **Goal**(사용자 생산성)에 어떻게 기여하는지 명시 없으면 "숫자만 관리"로 전락

---

## 5. 한눈 정리

```
전략 ─── Goal       "서비스 품질 향상"
         │
         ▼
         CSF        "신속 대응"  "고객 만족"
         │
         ▼
성과 ─── KPI        MTTR < 1h    CSAT ≥ 4.5
         │
         ▼
측정 ─── Metric     해결시간     만족도점수
         │
         ▼
데이터 ─ Measurement 47분        5점
```

---

## 한 줄 요약

**CSF는 필수 성공요인, KPI는 성공 판단 핵심지표, Metric은 모든 정량 지표, Measurement는 각 관측값.** Goal → CSF → KPI → Metric → Measurement로 내려가는 위계. KPI는 5~15개가 적정, 나머지는 Supporting Metric으로 분리.

---

## 관련 문서

- [ITSM KPI 및 메트릭](../itsm/05-kpi-metrics.md)
- [MTBF vs MTTR vs MTTF](mtbf_vs_mttr_vs_mttf.md)
- [SLA vs OLA vs UC vs XLA](sla_vs_ola_vs_uc_vs_xla.md)
- [Effectiveness vs Efficiency](effectiveness_vs_efficiency.md)
