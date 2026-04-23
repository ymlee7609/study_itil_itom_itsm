# ITIL 4/5 / ITSM / ITOM / ITAM 학습 자료

회사의 ITIL, ITSM, ITOM, ITAM 도입을 위한 체계적인 학습 자료 모음입니다. 2026년 2월 출시된 **ITIL 5 (디지털 제품 및 서비스 관리)** 내용도 포함합니다.

## 학습 추천 순서

1. **ITIL 4** - IT 서비스 관리의 기본 프레임워크 이해
2. **ITIL 5** - 디지털 제품 중심 + AI 거버넌스 + 경험 관리로의 진화
3. **ITIL 4 vs ITIL 5** - 두 버전의 차이와 전환 전략
4. **ITSM** - IT 서비스 관리의 실무 적용
5. **ITOM** - IT 운영 관리의 기술적 역량
6. **ITAM** - IT 자산의 전체 생애주기 관리

---

## 목차

### ITIL 4 (IT Infrastructure Library)

| 순서 | 문서 | 내용 |
|------|------|------|
| 1 | [ITIL 4 개요](docs/itil4/01-overview.md) | ITIL 역사, v3 vs v4 차이, 핵심 용어 |
| 2 | [7대 지도 원칙](docs/itil4/02-guiding-principles.md) | 가치 집중, 반복적 진행, 협업, 최적화 등 |
| 3 | [서비스 가치 시스템 (SVS)](docs/itil4/03-svs.md) | SVS 구조, 거버넌스, 지속적 개선 |
| 4 | [서비스 가치 사슬](docs/itil4/04-service-value-chain.md) | Plan, Engage, Design, Obtain, Deliver, Improve |
| 5 | [4가지 차원](docs/itil4/05-four-dimensions.md) | 조직/사람, 정보/기술, 파트너, 가치흐름 |
| 6 | [일반 관리 프랙티스](docs/itil4/06-practices-general.md) | 14개 General Management Practices |
| 7 | [서비스 관리 프랙티스](docs/itil4/07-practices-service.md) | 17개 Service Management Practices |
| 8 | [기술 관리 프랙티스](docs/itil4/08-practices-technical.md) | 3개 Technical Management Practices |
| 9 | [핵심 프로세스 심화](docs/itil4/09-key-processes.md) | 인시던트, 문제, 변경, 서비스 요청 관리 |
| 10 | [인증 체계](docs/itil4/10-certification.md) | Foundation, MP, SL, Master 경로 |

### ITIL 5 (Digital Product & Service Management, 2026)

| 순서 | 문서 | 내용 |
|------|------|------|
| 1 | [ITIL 5 개요](docs/itil5/01-overview.md) | ITIL 5란, 출시 배경, 핵심 변화, 신규 용어 |
| 2 | [제품 및 서비스 라이프사이클 (PSLM)](docs/itil5/02-product-service-lifecycle.md) | 8개 활동, SVC → PSLM 전환, 제품 중심 접근 |
| 3 | [AI 거버넌스와 6C 모델](docs/itil5/03-ai-governance.md) | Context, Capability, Confidence, Control, Collaboration, Continuity |
| 4 | [ITIL 5에서 유지되는 것들](docs/itil5/04-practices-continuity.md) | 34개 프랙티스, 7대 원칙, 4가지 차원의 연속성 |
| 5 | [거버넌스 변화와 경험 관리](docs/itil5/05-governance-experience.md) | 작업 위→곁, XLA, 서비스 관계 모델 |
| 6 | [ITIL 5 인증 체계](docs/itil5/06-certification.md) | 신규 자격 경로, ITIL 4 → 5 전환 가이드 |

### ITIL 4 vs ITIL 5 비교

| 문서 | 내용 |
|------|------|
| [종합 비교](docs/itil4-vs-itil5/01-comprehensive-comparison.md) | 프레임워크/모델/거버넌스/AI/인증/실무/전환 전략 8개 관점 비교 |

### ITSM (IT Service Management)

| 순서 | 문서 | 내용 |
|------|------|------|
| 1 | [ITSM 개요](docs/itsm/01-overview.md) | ITSM 정의, 프레임워크, 비즈니스 가치 |
| 2 | [ITSM vs ITIL 비교](docs/itsm/02-itsm-vs-itil.md) | 개념 차이, 상호보완적 관계 |
| 3 | [핵심 프로세스](docs/itsm/03-key-processes.md) | 서비스 데스크, SLA, CMDB, 자산 관리 |
| 4 | [도구 비교](docs/itsm/04-tools-comparison.md) | ServiceNow, Jira SM, BMC, Freshservice 등 |
| 5 | [KPI 및 메트릭](docs/itsm/05-kpi-metrics.md) | MTTR, FCR, SLA 준수율, CSAT |
| 6 | [모범 사례](docs/itsm/06-best-practices.md) | 도입 전략, 성숙도 모델, 자동화 |

### ITOM (IT Operations Management)

| 순서 | 문서 | 내용 |
|------|------|------|
| 1 | [ITOM 개요](docs/itom/01-overview.md) | ITOM 정의, 3대 핵심 기능, 비즈니스 가치 |
| 2 | [ITOM vs ITSM 비교](docs/itom/02-itom-vs-itsm.md) | 차이점, 통합 시너지 |
| 3 | [핵심 역량](docs/itom/03-capabilities.md) | 이벤트, 모니터링, 디스커버리, 서비스 매핑, 클라우드 |
| 4 | [도구 비교](docs/itom/04-tools-comparison.md) | ServiceNow ITOM, Datadog, Splunk, Nagios 등 |
| 5 | [AIOps 트렌드](docs/itom/05-aiops-trends.md) | AIOps, 예측 분석, 자율 운영 |

### ITAM (IT Asset Management)

| 순서 | 문서 | 내용 |
|------|------|------|
| 1 | [ITAM 개요](docs/itam/01-overview.md) | ITAM 정의, 3대 핵심 영역, 생애주기, 비즈니스 가치 |
| 2 | [ITAM vs ITSM vs ITOM 비교](docs/itam/02-itam-vs-itsm-itom.md) | 차이점 비교, 관계도, 실무 시나리오, 조직 설명 가이드 |
| 3 | [도입 사례 및 ROI](docs/itam/03-case-studies.md) | 칼스버그, BBC 등 글로벌/국내 사례, ROI 데이터, 도입 가이드 |

### 핵심 개념 (Key Concepts)

자주 혼동되지만 실무·감사·시험에서 명확히 구분해야 하는 **22개 용어쌍** 모음. 상세 가이드는 [key_concept/README.md](docs/key_concept/README.md) 참고.

#### P1 — 실무 최빈 혼동 (반드시 숙지)

| 문서 | 핵심 포인트 |
|------|-----------|
| [Output vs Outcome](docs/key_concept/output_vs_outcome.md) | 산출물 vs 결과, SLA/XLA의 뿌리 |
| [Incident vs Problem vs Known Error](docs/key_concept/incident_vs_problem_vs_known_error.md) | 증상 vs 원인 vs 원인+임시조치 |
| [Change vs Release vs Deployment](docs/key_concept/change_vs_release_vs_deployment.md) | 결정 vs 패키징 vs 실행 |
| [Utility vs Warranty](docs/key_concept/utility_vs_warranty.md) | Fit for Purpose vs Fit for Use |
| [SLA vs OLA vs UC vs XLA](docs/key_concept/sla_vs_ola_vs_uc_vs_xla.md) | 대외/내부/외주/경험 4층위 |
| [CI vs Asset](docs/key_concept/ci_vs_asset.md) | 서비스 관점 vs 재무 관점 |
| [Event vs Alert vs Incident](docs/key_concept/event_vs_alert_vs_incident.md) | ITOM → ITSM 감지 체인 |
| [Process vs Practice vs Function](docs/key_concept/process_vs_practice_vs_function.md) | v3→v4 용어 변화 |
| [Service Request vs Incident](docs/key_concept/service_request_vs_incident.md) | 정상 요청 vs 비정상 중단 |
| [Value vs Cost vs Risk](docs/key_concept/value_vs_cost_vs_risk.md) | 가치 공식 3요소 |

#### P2 — 개념 심화·인증 대비

| 문서 | 핵심 포인트 |
|------|-----------|
| [Customer vs User vs Sponsor](docs/key_concept/customer_vs_user_vs_sponsor.md) | 결정자·계약자·사용자 3역할 |
| [Workaround vs Fix vs Resolution](docs/key_concept/workaround_vs_fix_vs_resolution.md) | 임시 vs 증상 vs 근본 |
| [MTBF vs MTTR vs MTTF](docs/key_concept/mtbf_vs_mttr_vs_mttf.md) | 장애 지표 4형제 |
| [KPI vs Metric vs CSF](docs/key_concept/kpi_vs_metric_vs_csf.md) | CSF→KPI→Metric→Measurement |
| [Governance vs Management](docs/key_concept/governance_vs_management.md) | EDM 감독 vs Plan·Run 실행 |
| [Effectiveness vs Efficiency](docs/key_concept/effectiveness_vs_efficiency.md) | 효과성 > 효율성 > 경제성 (3E) |
| [Availability vs Reliability vs Maintainability](docs/key_concept/availability_vs_reliability_vs_maintainability.md) | 가용성 4요소 공식 |
| [RTO vs RPO vs MTD](docs/key_concept/rto_vs_rpo_vs_mtd.md) | BCM/DR 4대 시간 지표 |
| [Service vs Product vs Service Offering](docs/key_concept/service_vs_product_vs_offering.md) | ITIL 5 PSLM 축 |
| [CMDB vs CMS vs Asset Registry](docs/key_concept/cmdb_vs_cms.md) | CMS ⊃ CMDB, Asset 별도 |

#### P3 — 보충 지식

| 문서 | 핵심 포인트 |
|------|-----------|
| [Capacity vs Performance vs Demand](docs/key_concept/capacity_vs_performance_vs_demand.md) | 공급 vs 체감 vs 요구 |
| [Policy vs Standard vs Procedure](docs/key_concept/policy_vs_standard_vs_procedure.md) | 문서 4단 계층 |
| [Continual vs Continuous Improvement](docs/key_concept/continual_vs_continuous_improvement.md) | 철자 차이, ITIL 공식 용어 |

### 참고 자료

| 문서 | 내용 |
|------|------|
| [참고 자료 모음](docs/references/sources.md) | 공식 문서, 서적, 온라인 강의, 커뮤니티 링크 |

---

## 핵심 개념 요약

```
┌──────────────────────────────────────────────────────────────────────┐
│                   ITIL 4 (2019) → ITIL 5 (2026)                      │
│          IT 서비스 관리 → 디지털 제품 및 서비스 관리 (DPSM)              │
│             + AI 거버넌스 (6C) + 경험 관리 (XLA)                       │
├──────────────────┬──────────────────┬────────────────────────────────┤
│      ITSM        │      ITOM        │            ITAM               │
│ (서비스 전달/관리) │ (인프라/운영 관리) │      (IT 자산 관리)            │
│                  │                  │                                │
│ - 인시던트 관리   │ - 이벤트 관리     │ - 하드웨어 자산 관리            │
│ - 문제 관리      │ - 모니터링        │ - 소프트웨어 라이선스            │
│ - 변경 관리      │ - 디스커버리      │ - 클라우드 자산 관리             │
│ - 서비스 요청    │ - 서비스 매핑     │ - 자산 생애주기                 │
│ - SLA 관리      │ - 클라우드 관리   │ - 비용 최적화                   │
│ - 서비스 데스크   │ - AIOps          │ - 라이선스 준수                 │
│                  │                  │                                │
│ "프론트 오브      │ "비하인드 더 씬"  │ "재고/비용 관리자"              │
│  하우스"         │  (백엔드 운영)    │  (재무/계약/물리)               │
│ (사용자 대면)     │                  │                                │
└──────────────────┴──────────────────┴────────────────────────────────┘
```

---

> 이 자료는 2026년 4월 기준으로 작성되었으며, ITIL 5 (2026년 2월 출시) 내용을 포함합니다.
