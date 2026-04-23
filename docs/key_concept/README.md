# Key Concepts — ITIL 핵심 혼동 용어 모음

ITIL 4/5, ITSM, ITOM, ITAM 전반에서 **자주 혼용되지만 의미가 완전히 다른** 용어쌍을 정리한 디렉토리. 현장·조직 교육·시험 대비·감사 대응에 활용한다.

---

## 사용 순서 추천

조직에 ITIL을 처음 도입·설명할 때는 아래 순서로 학습하면 효과적이다.

1. **기본 개념 축** (서비스·가치): Output vs Outcome → Utility vs Warranty → Value vs Cost vs Risk
2. **관계자**: Customer vs User vs Sponsor
3. **실무 프로세스**: Incident vs Problem vs Known Error → Service Request vs Incident → Event vs Alert vs Incident → Change vs Release vs Deployment → Gate vs Guardrail → Workaround vs Fix vs Resolution
4. **계약·측정**: SLA vs OLA vs UC vs XLA → KPI vs Metric vs CSF → MTBF vs MTTR vs MTTF
5. **가용성·연속성**: Availability vs Reliability vs Maintainability → RTO vs RPO vs MTD → Capacity vs Performance vs Demand
6. **구조·문서 체계**: Process vs Practice vs Function → Governance vs Management → Policy vs Standard vs Procedure
7. **자산·구성**: CI vs Asset → CMDB vs CMS vs Asset Registry
8. **제품·개선**: Service vs Product vs Service Offering → Effectiveness vs Efficiency vs Economy → Continual vs Continuous Improvement

---

## 목차 (우선순위별)

### P1 — 실무 최빈 혼동 (반드시 숙지)

| 문서 | 카테고리 | 핵심 포인트 |
|------|---------|-----------|
| [Output vs Outcome](output_vs_outcome.md) | 서비스 가치 | 산출물 vs 결과. SLA/XLA의 뿌리 |
| [Incident vs Problem vs Known Error](incident_vs_problem_vs_known_error.md) | 실무 프로세스 | 증상 vs 원인 vs 원인+임시조치 |
| [Change vs Release vs Deployment](change_vs_release_vs_deployment.md) | 실무 프로세스 | 결정 vs 패키징 vs 실행 |
| [Gate vs Guardrail](gate_vs_guardrail.md) | Change Enablement | 사전 승인 vs 자동 경계, ITIL 5/DevOps 패러다임 변화 |
| [Utility vs Warranty](utility_vs_warranty.md) | 서비스 정의 | Fit for Purpose vs Fit for Use |
| [SLA vs OLA vs UC vs XLA](sla_vs_ola_vs_uc_vs_xla.md) | 계약 | 대외/내부/외주/경험 4층위 |
| [CI vs Asset](ci_vs_asset.md) | 자산·구성 | 서비스 관점 vs 재무 관점 |
| [Event vs Alert vs Incident](event_vs_alert_vs_incident.md) | 모니터링 | 감지 체인, ITOM→ITSM 경계 |
| [Process vs Practice vs Function](process_vs_practice_vs_function.md) | 구조 | v3→v4 용어 변화 |
| [Service Request vs Incident](service_request_vs_incident.md) | 실무 프로세스 | 정상 요청 vs 비정상 중단 |
| [Value vs Cost vs Risk](value_vs_cost_vs_risk.md) | 가치 공식 | 3요소 트레이드오프 |

### P2 — 개념 심화·인증 대비

| 문서 | 카테고리 | 핵심 포인트 |
|------|---------|-----------|
| [Customer vs User vs Sponsor](customer_vs_user_vs_sponsor.md) | 관계자 | 결정자·계약자·사용자 3역할 |
| [Workaround vs Fix vs Resolution](workaround_vs_fix_vs_resolution.md) | 해결 수준 | 임시 vs 증상 vs 근본 |
| [MTBF vs MTTR vs MTTF](mtbf_vs_mttr_vs_mttf.md) | 장애 지표 | 4형제 시간 축 위치 |
| [KPI vs Metric vs CSF](kpi_vs_metric_vs_csf.md) | 지표 계층 | CSF → KPI → Metric → Measurement |
| [Governance vs Management](governance_vs_management.md) | 거버넌스 | 감독(EDM) vs 실행(Plan·Run) |
| [Effectiveness vs Efficiency](effectiveness_vs_efficiency.md) | 3E 프레임 | 효과성 > 효율성 > 경제성 순 |
| [Availability vs Reliability vs Maintainability](availability_vs_reliability_vs_maintainability.md) | 가용성 | 4요소 공식, SLA 세분화 |
| [RTO vs RPO vs MTD](rto_vs_rpo_vs_mtd.md) | 비즈니스 연속성 | DR 4대 시간 지표 |
| [Service vs Product vs Service Offering](service_vs_product_vs_offering.md) | 서비스 정의 | 자원 vs 관계 vs 메뉴 |
| [CMDB vs CMS vs Asset Registry](cmdb_vs_cms.md) | 구성 관리 | CMS ⊃ CMDB, Asset은 별도 |

### P3 — 보충 지식

| 문서 | 카테고리 | 핵심 포인트 |
|------|---------|-----------|
| [Capacity vs Performance vs Demand](capacity_vs_performance_vs_demand.md) | 용량 관리 | 공급 vs 체감 vs 요구 |
| [Policy vs Standard vs Procedure vs Guideline](policy_vs_standard_vs_procedure.md) | 문서 체계 | 4단 계층·구속력 |
| [Continual vs Continuous Improvement](continual_vs_continuous_improvement.md) | 개선 | 철자 차이, ITIL 공식 용어 |

---

## 통계

- 총 23개 문서
- P1: 11개, P2: 10개, P3: 3개 (※ Output vs Outcome은 P1 포함)

---

## 활용 시나리오

| 상황 | 추천 문서 |
|------|-----------|
| 신규 ITIL 도입 교육 | P1 전체 + Service vs Product |
| 개발·운영 협업 갭 해소 | Change/Release/Deployment, Event/Alert/Incident, **Gate/Guardrail** |
| DevOps·SRE 전환 | **Gate/Guardrail**, Change/Release/Deployment, MTBF/MTTR |
| SLA 협상·재설계 | SLA/OLA/UC/XLA, Utility/Warranty, RTO/RPO |
| 감사·컴플라이언스 대응 | Governance/Management, Policy/Standard, CI/Asset, **Gate/Guardrail** |
| 지표·KPI 재정비 | KPI/Metric/CSF, MTBF/MTTR, Effectiveness/Efficiency |
| ITIL Foundation 시험 대비 | P1 + P2 전체 |

---

## 업데이트 계획

향후 실무에서 추가로 혼동이 발견되는 용어는 이 디렉토리에 누적한다. 추가 후보:
- Lead Time vs Cycle Time vs Throughput
- Baseline vs Benchmark
- Catalogue vs Portfolio
- Service vs Support vs Solution
- MTTR 세분화 (MTTD vs MTTA vs MTTI vs MTTR)
