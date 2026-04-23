# COBIT 거버넌스 vs 관리

COBIT의 **가장 핵심적이고 차별화된 구분**. COBIT 5부터 거버넌스(Governance)와 관리(Management)를 **명확히 분리**했고, COBIT 2019에서 이 분리가 더 강화됐다. ITIL이 주로 Management 영역을 다루는 반면, COBIT은 **Governance 영역을 독점적으로 정의**한다.

## 목차

- [1. 왜 분리하는가](#1-왜-분리하는가)
- [2. EDM 도메인 (거버넌스)](#2-edm-도메인-거버넌스)
- [3. APO·BAI·DSS·MEA 도메인 (관리)](#3-apobaidssmea-도메인-관리)
- [4. 거버넌스 바디의 역할](#4-거버넌스-바디의-역할)
- [5. 실무 시나리오](#5-실무-시나리오)
- [6. ITIL·ISO와의 대응](#6-itiliso와의-대응)

---

## 1. 왜 분리하는가

### 전통적 혼선

많은 조직에서 "IT 거버넌스"와 "IT 관리"가 **같은 사람·같은 회의체**에서 다뤄진다. 결과:
- 경영진이 **세부 운영에 매몰**되어 전략적 방향 설정 실패
- 관리자가 **전략적 결정권**까지 가지면서 책임 소재 불명확
- 감사 시 **누가 무엇을 결정했는지** 추적 불가

### COBIT의 해법

```
┌─────────────────────────────────────────────────┐
│  Governance (EDM: Evaluate · Direct · Monitor)  │
│  → 이사회 / 거버넌스 바디                          │
│  → "무엇이 올바른 방향인가?"                       │
│  → 위험 수용 한도, 전략, 감독                      │
└──────────────────┬──────────────────────────────┘
                   │ 방향·정책·제약
                   ▼
┌─────────────────────────────────────────────────┐
│  Management (APO · BAI · DSS · MEA)             │
│  → 경영층·관리자                                   │
│  → "어떻게 실행할 것인가?"                        │
│  → 계획·구축·운영·측정                            │
└──────────────────┬──────────────────────────────┘
                   │ 보고·성과·리스크
                   ▲
               (피드백 루프)
```

**핵심 원칙**: 두 활동은 **서로 다른 목적**을 가지며, **서로 다른 역할**에 의해 수행된다.

---

## 2. EDM 도메인 (거버넌스)

**EDM = Evaluate, Direct, Monitor** (평가·지시·감독)

거버넌스 바디(이사회 또는 그에 준하는 기구)가 수행하는 3가지 활동:

| 활동 | 의미 | 예시 질문 |
|------|------|----------|
| **Evaluate** | 현재 상황 평가 | "우리 IT 투자는 전략 목표에 기여하나?" |
| **Direct** | 방향·우선순위 지시 | "클라우드 우선 정책을 공식화하라" |
| **Monitor** | 이행 감독 | "분기별 IT 가치·리스크 KPI를 보고하라" |

### EDM 5개 목표 (COBIT 2019)

| 코드 | 목표 | 핵심 질문 |
|------|------|----------|
| **EDM01** | Ensured Governance Framework Setting and Maintenance | 거버넌스 프레임워크 자체는 잘 세팅됐나? |
| **EDM02** | Ensured Benefits Delivery | IT는 **가치**를 창출하는가? |
| **EDM03** | Ensured Risk Optimization | IT **리스크**는 수용 가능한 수준인가? |
| **EDM04** | Ensured Resource Optimization | IT **자원**(인력·예산·자산)은 최적 활용되는가? |
| **EDM05** | Ensured Stakeholder Engagement | **이해관계자**와의 소통은 충분한가? |

### EDM의 특징

- **오직 5개** (40개 전체 목표 중) — 거버넌스는 소수의 핵심 활동으로 구성
- **이사회 급**에서 수행 (CIO/CTO 레벨 아님)
- **분기~연간** 주기
- 산출물: **Policy, Direction, Risk Appetite Statement, Benefit Delivery Report**

---

## 3. APO·BAI·DSS·MEA 도메인 (관리)

**Management = Plan, Build, Run, Monitor** (계획·구축·운영·측정)

관리층(CIO·관리자)이 수행하는 4개 도메인, 총 35개 목표:

| 도메인 | 풀네임 | 의미 | 목표 수 |
|--------|--------|------|---------|
| **APO** | Align, Plan, Organize | 정렬·계획·조직 | 14개 |
| **BAI** | Build, Acquire, Implement | 구축·획득·구현 | 11개 |
| **DSS** | Deliver, Service, Support | 전달·서비스·지원 | 6개 |
| **MEA** | Monitor, Evaluate, Assess | 모니터링·평가·진단 | 4개 |

### 관리의 특징

- **35개 목표** — 실무 다양성 반영
- **CIO·관리자** 레벨 실행
- **일간·주간·월간** 주기
- 산출물: **Plan, Design, Report, Performance Metric**

---

## 4. 거버넌스 바디의 역할

### COBIT이 요구하는 거버넌스 바디 구성

| 역할 | 책임 |
|------|------|
| **Board of Directors / 이사회** | 최종 거버넌스 책임, EDM 수행 주체 |
| **IT Steering Committee** | IT 전략·투자·리스크 심의 |
| **Risk Committee** | 기업 전반 리스크 감독 (IT 포함) |
| **Audit Committee** | 감사 독립성, 통제 감독 |

### 의사결정 권한 분리 예시

| 결정 | 담당 |
|------|------|
| **IT 투자 전체 예산 상한** | 이사회 (Governance) |
| 특정 프로젝트 예산 할당 | CIO / Steering Committee (Management) |
| **리스크 수용 한도 정의** | 이사회 / Risk Committee (Governance) |
| 개별 리스크 수용·이전 결정 | 리스크 관리자 (Management) |
| **IT 아웃소싱 정책** | 이사회 (Governance) |
| 특정 벤더 선정·계약 | 구매팀·CIO (Management) |

---

## 5. 실무 시나리오

### 시나리오 1: 클라우드 전환

| 단계 | 거버넌스 (EDM) | 관리 (APO·BAI·DSS) |
|------|---------------|---------------------|
| 1. 방향 결정 | "3년 내 70% 클라우드 전환" 이사회 결의 | - |
| 2. 리스크 수용 | "데이터 국외 이전은 불허" (EDM03) | - |
| 3. 계획 수립 | - | APO02 전략 수립, APO05 포트폴리오 |
| 4. 구축 | - | BAI03 솔루션 식별, BAI07 변경 수용 |
| 5. 운영 | - | DSS01 운영, DSS02 서비스 요청 |
| 6. 감독 | EDM02 가치 측정 보고 수령 | MEA01 성과 보고 |

### 시나리오 2: 보안 침해 발생

| 단계 | 거버넌스 | 관리 |
|------|---------|------|
| 탐지 | - | DSS05 Managed Security Services |
| 대응 | - | DSS02 Managed Service Requests & Incidents |
| 이사회 보고 | **EDM03 Risk Optimization 재검토** | - |
| 정책 개정 | **EDM01 프레임워크 유지** | APO13 보안 관리 |
| 유사 사례 예방 | "보안 투자 한도 상향" 이사회 결의 | APO12 리스크 관리 개선 |

### 시나리오 3: 신기술(AI) 도입

| 결정 | 층위 |
|------|------|
| "AI를 전사 전략 우선순위로 설정" | Governance (EDM01) |
| "AI는 최종 인간 승인 필수" (윤리 원칙) | Governance (EDM03) |
| AI 프로젝트 로드맵 | Management (APO02, BAI11) |
| 특정 LLM 벤더 선정 | Management (APO10 Vendor Management) |
| AI 모델 성능 모니터링 | Management (DSS01, MEA01) |

---

## 6. ITIL·ISO와의 대응

| 영역 | COBIT | ITIL | ISO |
|------|-------|------|-----|
| **Governance** | **EDM 5개 목표** | 제한적 (SVS 내 거버넌스 개념) | ISO/IEC 38500 (IT 거버넌스) |
| **Management** | APO·BAI·DSS·MEA 35개 | **34 Practices** | ISO/IEC 20000 (SMS) |
| **Security** | APO13 / DSS05 | Information Security Management Practice | **ISO/IEC 27001** (ISMS) |
| **Risk** | APO12 / EDM03 | Risk Management Practice | ISO 31000 |

### 실무 통합 모델

```
┌─────────────────────────────────────────────┐
│  COBIT EDM (거버넌스)  ← 이사회·경영진         │
│  + ISO 38500 정렬                            │
└────────────────────┬────────────────────────┘
                     │
┌────────────────────▼────────────────────────┐
│  COBIT APO/BAI/DSS/MEA (관리)               │
│  + ITIL 34 Practices 세부 매핑               │
│  + ISO 20000/27001 통제                      │
└─────────────────────────────────────────────┘
```

→ 현실적 해법: **COBIT을 상위 거버넌스 프레임으로**, **ITIL·ISO를 실행 레이어로** 결합.

---

## 한 줄 요약

**COBIT은 거버넌스(EDM 5개 목표, 이사회 수행)와 관리(APO/BAI/DSS/MEA 35개 목표, CIO·관리자 수행)를 명확히 분리**한다. 거버넌스는 **"평가·지시·감독"**, 관리는 **"계획·구축·운영·측정"**. 이 분리가 COBIT이 ITIL과 구별되는 핵심이자, 감사·규제 대응의 기본 구조다.

---

## 관련 문서

- [COBIT 개요](01-overview.md)
- [COBIT 프레임워크 구조 (5 도메인·40 목표)](03-framework-structure.md)
- [Governance vs Management (핵심 개념)](../key_concept/governance_vs_management.md)
- [Gate vs Guardrail](../key_concept/gate_vs_guardrail.md)
- [ITIL vs COBIT 비교](06-itil-vs-cobit.md)
