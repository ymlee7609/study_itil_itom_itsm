# Effectiveness vs Efficiency vs Economy (3E)

"잘한다"의 3가지 다른 의미. 한국어로는 다 "효율"로 뭉개지기 쉬움. 의사결정 시 **무엇을 최적화하고 있는지** 명확히 해야 한다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 3E 공식](#2-3e-공식)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Effectiveness (효과성) | Efficiency (효율성) | Economy (경제성) |
|------|-----------------------|---------------------|-----------------|
| **정의** | 의도한 **결과를 달성**하는 정도 | 투입 자원 **대비 산출** 비율 | 자원을 **저가에 확보** |
| **질문** | "제대로 된 것을 하는가?" (Doing the right things) | "제대로 하는가?" (Doing things right) | "싸게 사는가?" (Cheap acquisition) |
| **측정** | Outcome 달성률 | Output / Input | 단가, 원가 |
| **최적화 대상** | 목표 | 프로세스 | 비용 |

---

## 2. 3E 공식

```
                    목표 (Goal)
                         │
                         ▼
         ┌───────────Effectiveness────────────┐
         │  "옳은 결과를 달성했는가?"            │
         │  Outcome 중심                       │
         └─────────────────────────────────────┘
                         │
                         ▼
         ┌────────────Efficiency──────────────┐
         │  "자원을 효과적으로 썼는가?"          │
         │  Output / Input                    │
         └─────────────────────────────────────┘
                         │
                         ▼
         ┌─────────────Economy────────────────┐
         │  "자원을 싸게 구했는가?"             │
         │  단가 최소화                         │
         └─────────────────────────────────────┘
```

**핵심 서열**: Effectiveness > Efficiency > Economy

- 틀린 것을 싸게·빨리 하는 건 의미 없다
- 먼저 **옳은 것**을 하고, 그 다음 **효율**을 높이고, 마지막으로 **원가**를 낮춤

---

## 3. 실무 예시

### 예시 1: 장애 대응 도구 도입

| 3E | 질문 | 답변 |
|-----|------|------|
| **Effectiveness** | 장애 복구 시간이 실제로 줄었나? | MTTR 40분 → 25분 (38% 개선) ✓ |
| **Efficiency** | 도입한 리소스(담당자 시간, 교육비) 대비 성과 충분한가? | 담당자 10명 × 20시간 투입 대비 성과 적정 ✓ |
| **Economy** | 그 도구를 싸게 샀나? | 경쟁 제품 대비 20% 저렴 ✓ |

→ 3E 모두 충족 = 이상적.

### 예시 2: 3E 충돌

| 시나리오 | 평가 |
|---------|------|
| 저가 외주로 서비스 데스크 운영 | Economy ✓, Effectiveness ✗ (응답 품질 하락) |
| 대형 ITSM 도구 풀 활용 안 하면서 유지 | Economy ✗, Effectiveness ? |
| 최적화된 프로세스 but 잘못된 목표 | Efficiency ✓, Effectiveness ✗ |

### 예시 3: 실제 KPI 매핑

| 영역 | KPI | 3E 종류 |
|------|-----|---------|
| Incident | SLA 준수율, 재발률 | Effectiveness |
| Incident | 티켓당 처리 비용, 건당 소요시간 | Efficiency |
| Incident | 인력 인건비, 도구 구매가 | Economy |
| Change | 성공률 | Effectiveness |
| Change | Change당 리소스 | Efficiency |
| Change | CI/CD 파이프라인 비용 | Economy |

---

## 4. 왜 이 구분이 중요한가

### (1) "비용 절감" 함정

- "20% 절감했다" 선언 → Economy 개선
- 그러나 서비스 품질 하락 → Effectiveness 악화
- **3E 전체를 함께 봐야** 진짜 개선 판단 가능

### (2) 개선 우선순위

드러커의 유명한 원칙:

> "Efficiency is doing things right; **effectiveness is doing the right things**."  
> — Peter Drucker

→ 효율화 전에 **올바른 일인지** 먼저 점검.

### (3) CFO vs CIO 관점 차이

- **CFO 관점**: Economy + Efficiency 강조
- **CIO 관점**: Effectiveness 강조 (비즈니스 가치)
- 대화 시 **어느 E를 논의 중인지 명시** 필수

### (4) 공공기관 3E 감사

한국 감사원·영국 NAO 등은 IT 사업을 3E 관점으로 감사:
- 효과성 (정책 목표 달성)
- 효율성 (자원 활용)
- 경제성 (저가 확보)
- **셋 중 하나만 부실해도 지적** → 3E 균형 필수

### (5) ITIL 지속적 개선 원칙 연결

CSI/Continual Improvement 7단계:
1. What is the vision? → Effectiveness 방향
2. Where are we now? → 현 상태
3. Where do we want to be? → Effectiveness 목표
4. How do we get there? → Efficiency·Economy 수단
5. Take action → 실행
6. Did we get there? → Effectiveness 측정
7. How do we keep the momentum? → 지속

---

## 5. 한눈 정리

```
먼저 판단해야 할 순서

1. Effectiveness  → "올바른 일인가?"
2. Efficiency     → "잘 하고 있는가?"
3. Economy        → "싸게 사는가?"

 ※ 잘못된 순서: Economy만 최적화 → 전체 실패
```

---

## 한 줄 요약

**Effectiveness는 "올바른 것을 하는가", Efficiency는 "제대로 하는가", Economy는 "싸게 사는가".** 순서가 중요하다 — 틀린 것을 싸고 효율적으로 하는 건 의미 없다. 공공 IT 감사의 3E 프레임은 이 순서를 따른다.

---

## 관련 문서

- [Output vs Outcome](output_vs_outcome.md)
- [Value vs Cost vs Risk](value_vs_cost_vs_risk.md)
- [KPI vs Metric vs CSF](kpi_vs_metric_vs_csf.md)
- [ITIL 4 7대 지도 원칙](../itil4/02-guiding-principles.md)
