# MTBF vs MTTR vs MTTF vs MTTD

알파벳 비슷해서 거의 다 섞어 쓰는 **장애 지표 4대 형제**. 각각 측정 구간과 목적이 완전히 다르다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 시간 축 위치](#2-시간-축-위치)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 지표 | 풀네임 | 측정 구간 | 무엇을 말하나 |
|------|--------|-----------|--------------|
| **MTBF** | Mean Time **B**etween **F**ailures | 장애 종료 → 다음 장애 발생 | 고장 간 평균 간격 (**신뢰성**) |
| **MTTR** | Mean Time **T**o **R**epair (또는 Recover/Restore) | 장애 발생 → 복구 완료 | 복구에 걸린 평균 시간 (**유지보수성**) |
| **MTTF** | Mean Time **T**o **F**ailure | 새 가동 시작 → **첫** 고장 | 수리 불가 부품의 수명 (**내구성**) |
| **MTTD** | Mean Time **T**o **D**etect | 장애 발생 → 감지 | 감지 능력 (**관측성**) |

---

## 2. 시간 축 위치

```
 서비스 시작       장애 발생      감지        복구완료      다음 장애
     │              │            │             │             │
     │◄── 가동 ────►│            │             │◄── 가동 ───►│
     │              │            │             │             │
     │              │◄── MTTD ──►│             │             │
     │              │                          │             │
     │              │◄──────── MTTR ─────────►│             │
     │                                         │             │
     │                                         │◄── MTBF ──►│
     │                                                       │
     │◄────────── MTTF (수리 불가 부품의 수명) ──────────────►│
```

**핵심**:
- MTBF = **복구 후** 다음 장애까지 (수리 가능 시스템)
- MTTF = 처음부터 첫 고장까지 (수리 불가, 예: HDD 수명)
- MTTR = 발생 → 복구
- MTTD = 발생 → 감지 (MTTR의 부분)

### Availability (가용성) 공식

```
Availability = MTBF / (MTBF + MTTR)
```

- MTBF ↑ 또는 MTTR ↓ → 가용성 ↑

---

## 3. 실무 예시

### 예시 1: 웹서비스 가용성 계산

| 측정값 | 수치 |
|--------|------|
| 월 가동시간 | 720시간 |
| 월 장애 건수 | 3건 |
| MTBF | (720 − 장애시간) / 3 ≈ 240시간 |
| 평균 MTTR | 20분 |
| MTTD | 2분 |
| **Availability** | 720 / (720 + 1h) ≈ **99.86%** |

### 예시 2: 지표 개선 방향

| 문제 | 개선 대상 | 수단 |
|------|----------|------|
| "자주 터진다" | **MTBF** ↑ | 신뢰성 엔지니어링, 중복화, 부하 분산, 변경 품질 |
| "터지면 오래 간다" | **MTTR** ↓ | 자동 롤백, Runbook, Chaos Engineering, 포스트모템 |
| "터진 것도 한참 후 알았다" | **MTTD** ↓ | 모니터링 커버리지, 경보 임계값, SRE 관측성 |
| "디스크 1년 쓰면 고장" | **MTTF** ↑ | 하드웨어 등급 상향, 예방 교체 |

### 예시 3: SRE 관점 Golden Signals와의 연결

- SRE 4대 Golden Signal: Latency, Traffic, Errors, Saturation
- MTTD는 **Errors·Saturation 감지 속도**에 의존
- MTTR은 **런북·자동화 수준**에 의존

---

## 4. 왜 이 구분이 중요한가

### (1) SLA 보고서 왜곡 방지

- "MTTR 30분"만 보고 좋은 운영이라 판단 → 함정
- MTBF가 짧으면 (자주 터지면) 가용성은 여전히 낮음
- **두 지표를 나란히** 봐야 진단 가능

### (2) 투자 방향 결정

| 조직 유형 | 집중 투자 지표 |
|----------|---------------|
| 스타트업/초기 서비스 | MTBF (안정성 확보) |
| 성숙 서비스 | MTTR (장애 대응 체계) |
| 핵심 인프라 | MTTD + MTTR (관측성+자동화) |
| 하드웨어 집약적 | MTTF (수명 관리) |

### (3) DORA Metrics와의 관계

DORA 4대 메트릭:
- Deployment Frequency
- Lead Time for Changes
- **MTTR** (Mean Time to Restore) ← 동일 개념
- Change Failure Rate

→ MTTR은 DevOps 성숙도 지표로 직결.

### (4) MTTR의 세분화 (고급)

실무에서는 MTTR을 더 쪼갬:

| 지표 | 의미 |
|------|------|
| MTTD (Detect) | 발생 → 감지 |
| MTTA (Acknowledge) | 감지 → 담당자 확인 |
| MTTI (Investigate) | 확인 → 원인 파악 |
| MTTR (Repair) | 원인 파악 → 복구 |

- 병목이 어디인지 분해 분석 가능
- 예: MTTD 2분·MTTA 30분 → **대기 시간 단축**이 개선 포인트

### (5) MTBF의 맹점

- MTBF는 **평균**. 대장애 1건 + 소장애 다수가 섞이면 왜곡
- 따라서 **MTBF + 장애 규모 분포**를 같이 봐야 함
- 대안: SLO (Service Level Objective) 기반 에러 예산 사용

---

## 5. 한눈 정리

```
   발생 전         발생        감지        복구         다음 발생
    ──────────────┼──────────┼──────────┼──────────────┼──
                   │          │          │              │
      MTTF ──────►│          │          │              │
    (수명)         │──MTTD──►│          │              │
                   │──────MTTR────────►│              │
                              │                         │
                              │◄────── MTBF ──────────►│
                              │    (복구 후 다음까지)
```

---

## 한 줄 요약

**MTBF는 신뢰성(얼마나 자주 터지나), MTTR은 유지보수성(얼마나 빨리 복구하나), MTTF는 내구성(수리 불가 부품 수명), MTTD는 관측성(얼마나 빨리 감지하나).** 가용성 = MTBF / (MTBF + MTTR).

---

## 관련 문서

- [Availability vs Reliability vs Maintainability](availability_vs_reliability_vs_maintainability.md)
- [Incident vs Problem vs Known Error](incident_vs_problem_vs_known_error.md)
- [KPI vs Metric vs CSF](kpi_vs_metric_vs_csf.md)
- [ITSM KPI 및 메트릭](../itsm/05-kpi-metrics.md)
