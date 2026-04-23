# ITIL vs COBIT 비교

"둘 다 IT 프레임워크"로 뭉뚱그리면 실패한다. 관점·대상·산출물·조직 위치가 완전히 다르며, **경쟁 관계가 아니라 보완 관계**다. 현대 기업은 둘을 함께 사용한다.

## 목차

- [1. 한눈에 보는 차이](#1-한눈에-보는-차이)
- [2. 관점의 차이](#2-관점의-차이)
- [3. 영역 커버리지 비교](#3-영역-커버리지-비교)
- [4. 실무 결합 모델](#4-실무-결합-모델)
- [5. 어느 쪽부터 도입해야 하나](#5-어느-쪽부터-도입해야-하나)
- [6. 용어·개념 대응표](#6-용어개념-대응표)
- [7. 오해와 진실](#7-오해와-진실)

---

## 1. 한눈에 보는 차이

| 항목 | ITIL | COBIT |
|------|------|-------|
| **개발 기관** | PeopleCert (영국) | ISACA (미국) |
| **최신 버전** | ITIL 4 (2019), ITIL 5 (2026) | COBIT 2019 |
| **핵심 영역** | **Management** (서비스 운영) | **Governance** (감독·통제) |
| **주요 질문** | "어떻게 서비스를 잘 운영할까?" | "IT가 비즈니스에 기여하는가? 통제되고 있나?" |
| **대상 사용자** | Service Manager, 운영팀, DevOps | CIO, 감사인, 리스크 관리자, 이사회 |
| **산출물** | SLA, Runbook, Practice, 운영 지표 | Policy, Risk Appetite, 감사 증거, Capability Score |
| **주기** | 일·주·월간 (운영) | 분기·연간 (감독) |
| **측정 대상** | 서비스 품질 | 거버넌스 성숙도 |
| **프랙티스·목표 수** | ITIL 4: 34 Practices | COBIT 2019: 40 Objectives |
| **구성 개념** | Service Value Chain, 4 Dimensions | 40 Objectives × 7 Components |
| **감사 인정도** | 중간 | **높음** (공식 감사 기준) |

---

## 2. 관점의 차이

### 두 프레임워크의 초점

```
   비즈니스 목표
        │
        ▼
┌─────────────────┐
│   COBIT         │  ← "IT가 맞는 방향인가?"
│   Governance    │     (전략·리스크·통제)
│   (상위 관점)    │
└────────┬────────┘
         │ 방향·정책·한도
         ▼
┌─────────────────┐
│   ITIL          │  ← "IT를 어떻게 운영하나?"
│   Management    │     (서비스 전달)
│   (실행 관점)    │
└────────┬────────┘
         │ 성과·리스크 보고
         ▲
      (피드백)
```

### 비유

- **COBIT** = 선박의 **선장·항해일지**: 목적지·항로·안전을 책임
- **ITIL** = 선박의 **기관실·갑판**: 엔진·밧줄·조리 등 실제 운항

---

## 3. 영역 커버리지 비교

### 공통 영역 vs 고유 영역

```
                    공통 영역
                  ┌──────────┐
            ITIL  │   겹침   │  COBIT
         ┌───────┤ (운영 통제) ├───────┐
         │       │ BAI·DSS   │       │
    ITIL 전용 ◄──┤   영역    ├──► COBIT 전용
    (실무)       └──────────┘      (거버넌스)
     34 Practices                   EDM, MEA 영역
```

### 영역별 우위

| 영역 | 더 강한 프레임워크 |
|------|-------------------|
| 인시던트·문제 관리 | **ITIL** (상세 프로세스) |
| 변경 관리 실무 | ITIL + COBIT (BAI06 매핑) |
| 서비스 카탈로그·SLA | **ITIL** |
| **이사회 거버넌스** | **COBIT** (EDM) |
| **리스크 관리 체계** | **COBIT** (APO12, EDM03) |
| **규제 준수** | **COBIT** (MEA03) |
| **감사 증거 체계** | **COBIT** (Capability Level) |
| **IT 전략 수립** | COBIT (APO02) |
| **운영 자동화·DevOps** | ITIL + DASA DevOps |
| **경험 관리 (XLA)** | **ITIL 5** (COBIT은 약함) |

---

## 4. 실무 결합 모델

### 계층적 결합 (권장)

```
┌──────────────────────────────────────────────┐
│  Layer 1: Enterprise Strategy                │
│  - BSC, OKR                                  │
└──────────────────┬───────────────────────────┘
                   │
┌──────────────────▼───────────────────────────┐
│  Layer 2: IT Governance (COBIT 2019)         │
│  - EDM 5 목표 (이사회)                        │
│  - Capability Level 목표 설정                  │
│  - 11 Design Factors로 맞춤화                 │
└──────────────────┬───────────────────────────┘
                   │
┌──────────────────▼───────────────────────────┐
│  Layer 3: IT Management                      │
│  - COBIT APO/BAI/DSS/MEA (거버넌스 통제 관점)  │
│  - ITIL 34 Practices (실무 운영 관점)          │
│  - ISO 20000/27001 인증 요건                  │
└──────────────────┬───────────────────────────┘
                   │
┌──────────────────▼───────────────────────────┐
│  Layer 4: Operations                         │
│  - DevOps, SRE, AIOps                        │
│  - Kanban, Agile, Lean                       │
└──────────────────────────────────────────────┘
```

### 실무 운영 방식

| 레벨 | 프레임워크 | 주기 |
|------|----------|------|
| 이사회·경영진 | COBIT EDM | 분기 |
| CIO·감사·리스크 | COBIT APO/MEA | 월간 |
| 서비스 매니저 | **ITIL 34 Practices** | 주간·일간 |
| 운영·DevOps | ITIL + DORA/SRE | 실시간 |

### 대응표 예시: 변경 관리

| 층위 | 활동 | 프레임워크 |
|------|------|-----------|
| 이사회 | "Standard Change 정책 수용 한도 결정" | COBIT **EDM03** |
| 감사 | "변경 감사 로그 증거 확보" | COBIT **MEA04** |
| CIO | "Change Enablement 전반 전략" | COBIT **BAI06** |
| 관리자 | "CAB 운영, 변경 분류 기준" | COBIT BAI06 + ITIL Change Enablement |
| 실무 | "RFC 작성, 승인 루틴, Deployment" | **ITIL** Change Enablement + Deployment |

---

## 5. 어느 쪽부터 도입해야 하나

### 조직 유형별 권장 시작점

| 조직 유형 | 1순위 | 2순위 | 이유 |
|----------|-------|-------|------|
| **운영 혼란형** (인시던트·SLA 이슈) | ITIL | COBIT | 즉시 개선 가능한 운영 체계 우선 |
| **감사 지적·규제 대응형** | **COBIT** | ITIL | 거버넌스 증거 체계가 급선무 |
| **신규 IT 조직** | ITIL | COBIT | 기본 운영 먼저 |
| **대기업·금융·공공** | **COBIT** | ITIL | 거버넌스 요구 강함 |
| **스타트업·SMB** | ITIL (경량) | COBIT SMB | 운영 성숙도 우선 |

### 성숙도별 경로

```
Level 0: 아무것도 없음
   ↓
Level 1: ITIL 핵심 프랙티스 (Incident, Change, Problem)
   ↓
Level 2: ITIL 확장 + COBIT 일부 (APO09 SLA, APO12 Risk)
   ↓
Level 3: COBIT 본격 도입 (EDM 포함) + ITIL 4/5 전반
   ↓
Level 4: 통합 거버넌스 (COBIT 주도 + ITIL 실행)
   ↓
Level 5: 지속 개선 (AIOps, XLA, AI Governance)
```

---

## 6. 용어·개념 대응표

| COBIT 2019 | ITIL 4 | 차이 |
|-----------|--------|------|
| 40 Governance/Management Objectives | 34 Practices | COBIT은 통제 관점, ITIL은 실무 관점 |
| EDM (5 목표) | SVS 내 Governance 언급 | **COBIT이 압도적 상세** |
| APO09 Managed Service Agreements | Service Level Management Practice | 개념 동일 |
| APO12 Managed Risk | Risk Management Practice | COBIT이 전사 리스크, ITIL은 서비스 리스크 |
| APO13 Managed Security | Information Security Management Practice | 영역 동일, 접근 다름 |
| BAI06 Managed IT Changes | Change Enablement Practice | ITIL이 실무 상세 |
| BAI09 Managed Assets | IT Asset Management Practice | 동일 |
| BAI10 Managed Configuration | Service Configuration Management | 동일 |
| DSS02 Managed Service Requests and Incidents | Incident Mgmt + Service Request Mgmt | ITIL이 2개로 분리 |
| DSS03 Managed Problems | Problem Management | 동일 |
| DSS04 Managed Continuity | Service Continuity Management | 동일 |
| DSS05 Managed Security Services | Information Security Management (운영) | 영역 동일 |
| MEA03 Managed Compliance with External Requirements | - | **ITIL에 없음** |
| MEA04 Managed Assurance | - | **ITIL에 없음** |
| Capability Level 0~5 | (없음, CSI만 유사) | COBIT 고유 |

---

## 7. 오해와 진실

### 오해 1: "둘 중 하나만 선택하면 된다"

**진실**: 중대 기업일수록 **둘 다** 사용. 감사는 COBIT 증거를 요구하고, 실무는 ITIL이 상세. 배타 관계가 아님.

### 오해 2: "COBIT은 너무 무겁다"

**진실**: COBIT 5까지는 그랬으나 **COBIT 2019의 Design Factors**로 맞춤화 가능. SMB Focus Area 활용 시 경량 적용 가능.

### 오해 3: "ITIL만 있으면 감사 대응 가능"

**진실**: ITIL은 **Governance 영역(EDM·MEA)을 실질적으로 다루지 않음**. SOX·Basel·ISMS 감사는 COBIT 또는 동급 거버넌스 프레임워크 증거를 요구한다.

### 오해 4: "COBIT은 문서만 많고 실효성 없다"

**진실**: COBIT이 **실행 상세**를 직접 제공하지 않는 것은 사실이나, 그 실행 상세를 **ITIL·ISO로 채우라**는 것이 공식 설계 의도. "What"(COBIT) + "How"(ITIL)의 분업.

### 오해 5: "ITIL 5가 나오면 COBIT은 필요 없다"

**진실**: ITIL 5가 **Governance 언급을 강화**했지만(작업 위→곁), **EDM 수준의 거버넌스 체계**는 여전히 COBIT 고유. ITIL 5는 ITIL 4 진화형이지 COBIT 대체 아님.

### 오해 6: "COBIT은 이사회 문서라 IT 담당과 무관"

**진실**: COBIT 목표 40개 중 **35개는 Management 영역**이며 CIO·IT 관리자의 직접 책임. "COBIT = 이사회용"은 EDM 5개에만 해당.

---

## 한 줄 요약

**ITIL은 Management(운영 실무) 프레임워크, COBIT은 Governance(감독·통제) 프레임워크**로 **경쟁 관계가 아닌 보완 관계**다. 대기업·규제 산업일수록 COBIT 상위 레이어 + ITIL 실행 레이어의 결합이 표준이며, COBIT은 감사·규제 대응에서 ITIL이 채울 수 없는 고유 영역(EDM, MEA)을 독점한다.

---

## 관련 문서

- [COBIT 개요](01-overview.md)
- [COBIT 거버넌스 vs 관리](02-governance-vs-management.md)
- [COBIT 프레임워크 구조](03-framework-structure.md)
- [COBIT 도입 가이드](07-implementation.md)
- [Governance vs Management (핵심 개념)](../key_concept/governance_vs_management.md)
- [Process vs Practice vs Function](../key_concept/process_vs_practice_vs_function.md)
- [ITIL 4 개요](../itil4/01-overview.md)
- [ITIL 5 거버넌스 변화](../itil5/05-governance-experience.md)
