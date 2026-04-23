# Availability vs Reliability vs Maintainability vs Serviceability

"가용성"이라는 한 단어로 뭉뚱그려 쓰지만, ITIL의 가용성은 **3~4가지 하위 개념의 함수**다. 계약·SLA·아키텍처 설계 시 세분화 필수.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 4요소 공식](#2-4요소-공식)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Availability | Reliability | Maintainability | Serviceability |
|------|-------------|-------------|-----------------|----------------|
| **한국어** | 가용성 | 신뢰성 | 유지보수성 | 지원성 |
| **정의** | **합의된 시간에** 서비스가 작동할 확률 | 장애 없이 **연속 작동**하는 능력 | 장애 시 **복구 가능성** | **외부 공급자**의 지원 품질 |
| **질문** | "되는 시간이 얼마나?" | "얼마나 오래 안 죽나?" | "죽으면 얼마나 빨리 살리나?" | "벤더가 도와주나?" |
| **핵심 지표** | Uptime % | MTBF | MTTR | 벤더 SLA, 부품 조달 시간 |
| **단위** | 99.9% 등 | 시간 | 시간 | SLA 조항 |

---

## 2. 4요소 공식

```
                   Availability
                   (가용성)
                        │
           ┌────────────┴────────────┐
           │                         │
       Reliability              Maintainability
       (신뢰성)                 (유지보수성)
           │                         │
       MTBF ↑                    MTTR ↓
       "자주 안 죽게"            "빨리 살리게"
                        │
                        ▼
                   Serviceability
                   (지원성)
                   벤더·외부·부품
                   "지원 받을 수 있나"
```

### 공식

```
Availability = MTBF / (MTBF + MTTR)
```

- **Reliability 개선** (MTBF↑): 신뢰성 엔지니어링, 이중화, 변경 품질
- **Maintainability 개선** (MTTR↓): 자동 복구, Runbook, 모니터링
- **Serviceability 개선**: 프리미엄 벤더 계약, 예비 부품 확보

---

## 3. 실무 예시

### 예시 1: 가용성 99.9% 달성 방법

| 접근 | 수단 | 효과 |
|------|------|------|
| Reliability ↑ | 서버 이중화, Active-Active 구성 | 단일 장애점 제거 |
| Maintainability ↑ | 자동 failover, 30분 Runbook | 복구 시간 단축 |
| Serviceability ↑ | Dell ProSupport Plus (4시간 출동) | 하드웨어 교체 지연 최소 |
| **합성 결과** | MTBF 2,000h, MTTR 0.5h | Availability = 99.97% |

### 예시 2: 99.99% vs 99.999% 차이

| 레벨 | 연간 다운타임 허용 | 실무 의미 |
|------|-------------------|----------|
| 99% | 3일 15시간 | 사내 테스트 환경 |
| 99.9% ("three nines") | 8시간 45분 | 일반 엔터프라이즈 서비스 |
| 99.99% ("four nines") | 52분 | 결제·핵심 시스템 |
| 99.999% ("five nines") | **5분 15초** | 통신·금융 트레이딩 |

→ 9가 하나 추가될 때마다 **Reliability + Maintainability + Serviceability 모두** 10배 강화 필요.

### 예시 3: 동일 가용성, 다른 구조

| 시나리오 | MTBF | MTTR | Availability | 체감 |
|---------|------|------|-------------|------|
| A | 10,000h | 10h | 99.9% | 드물지만 크게 아플 때 오래 |
| B | 100h | 0.1h | 99.9% | 자주 죽지만 순식간에 복구 |

→ 같은 99.9%지만 사용자 경험은 완전히 다름. **양 지표를 구분해야** 진단 가능.

---

## 4. 왜 이 구분이 중요한가

### (1) SLA 협상 정교화

- "99.9% 가용성" 한 줄 계약은 너무 거칠다
- **명시할 항목**:
  - 연/월 다운타임 한도 (Availability)
  - 단일 장애 최대 지속시간 (Maintainability)
  - 연간 최대 장애 건수 (Reliability)
  - 벤더 응답 시간 (Serviceability)

### (2) 아키텍처 투자 방향 결정

| 문제 증상 | 투자 대상 |
|----------|----------|
| 자주 터지지만 금방 복구 | **Reliability** (이중화, 테스트, SRE) |
| 드물지만 터지면 오래 | **Maintainability** (자동화, 관측성) |
| 하드웨어 고장 시 대기시간 긺 | **Serviceability** (벤더 계약 상향) |

### (3) Cloud-Native 시대의 재해석

- 전통: 서버 Reliability (한 대를 오래 살게)
- Cloud: **Pod Replaceability** (자주 죽어도 즉시 재생성)
- → Reliability 개념이 **Resilience(복원력)**로 진화

### (4) "숨은 Serviceability" 인식

- 클라우드 서비스 장애 시 복구는 **AWS/Azure의 Serviceability**에 의존
- 자사 MTTR 수치는 **벤더 Serviceability에 종속됨**
- Multi-Cloud, Multi-Region 전략은 Serviceability 리스크 분산

### (5) Availability ≠ Performance

- 서버 가동 중이지만 응답 10초 → Availability 상 100%
- **사용자 체감**은 완전히 "안 됨"
- → Availability는 최소 조건, Performance·Latency는 별도 지표

### (6) ITIL Availability Management 프랙티스

- Availability Management = 4요소 모두 관리
- 단순히 "가동률 추적"이 아닌 **구조적 분석**
- Availability Plan = 위 4요소별 개선 로드맵

---

## 5. 한눈 정리

```
Availability (가용성)  =  MTBF  /  (MTBF + MTTR)
                          │              │
                    Reliability     Maintainability
                      (신뢰성)       (유지보수성)
                          │              │
                          ▼              ▼
                    "얼마나 오래"   "얼마나 빨리"
                    안 죽나         살리나
                          
                          
                    Serviceability
                    (지원성)
                    외부 벤더 / 부품 / 계약
```

---

## 한 줄 요약

**Availability는 가용 시간 비율, Reliability는 고장 간 간격(MTBF), Maintainability는 복구 속도(MTTR), Serviceability는 외부 공급자의 지원.** Availability = MTBF / (MTBF + MTTR) 공식으로 연결되며, Serviceability는 뒤에서 받쳐주는 외부 변수.

---

## 관련 문서

- [MTBF vs MTTR vs MTTF](mtbf_vs_mttr_vs_mttf.md)
- [SLA vs OLA vs UC vs XLA](sla_vs_ola_vs_uc_vs_xla.md)
- [Utility vs Warranty](utility_vs_warranty.md)
- [ITIL 4 서비스 관리 프랙티스](../itil4/07-practices-service.md)
