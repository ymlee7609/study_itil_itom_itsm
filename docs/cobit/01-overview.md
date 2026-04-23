# COBIT 개요

## 목차

- [1. COBIT이란](#1-cobit이란)
- [2. 역사와 버전 진화](#2-역사와-버전-진화)
- [3. COBIT 2019의 핵심 특징](#3-cobit-2019의-핵심-특징)
- [4. COBIT의 6가지 거버넌스 시스템 원칙](#4-cobit의-6가지-거버넌스-시스템-원칙)
- [5. 왜 기업은 COBIT을 채택하는가](#5-왜-기업은-cobit을-채택하는가)
- [6. 적용 대상](#6-적용-대상)

---

## 1. COBIT이란

**COBIT**(Control Objectives for Information and Related Technologies)은 **ISACA**(Information Systems Audit and Control Association)가 개발·유지하는 **엔터프라이즈 IT 거버넌스 및 관리 프레임워크**다.

| 항목 | 내용 |
|------|------|
| 정식 명칭 | Control Objectives for Information and Related Technologies |
| 관리 기관 | ISACA (미국 본부, 188개국 회원) |
| 현재 버전 | **COBIT 2019** (2018~2019년 발표) |
| 핵심 영역 | **엔터프라이즈 IT 거버넌스** (EGIT) |
| 대상 | CIO, CISO, IT 감사인, 리스크 관리자, 경영진 |
| 인증 | COBIT 2019 Foundation / Design & Implementation / Assessor |

### 한 줄 정의

> COBIT은 **비즈니스 목표를 IT 목표로 정렬**하고 **IT가 가치를 창출하도록 통제·감독**하는 **거버넌스 프레임워크**다.

---

## 2. 역사와 버전 진화

```
1996       1998       2000       2005       2007       2012       2018-2019
 │          │          │          │          │          │            │
 ▼          ▼          ▼          ▼          ▼          ▼            ▼
COBIT 1  COBIT 2   COBIT 3    COBIT 4    COBIT 4.1  COBIT 5      COBIT 2019
감사 중심  통제 확장  관리 포함   IT 거버넌스 프로세스    통합·거버넌스  설계·측정 현대화
                             등장      개선               차별화
```

| 버전 | 발표 | 주요 변화 |
|------|------|----------|
| **COBIT 1~3** (1996~2000) | - | 내부 통제·감사 중심 |
| **COBIT 4 / 4.1** (2005/2007) | - | IT 거버넌스 프로세스 프레임워크로 확장 |
| **COBIT 5** (2012) | - | 단일 통합 프레임워크, **거버넌스와 관리 명확 분리** |
| **COBIT 2019** (2018~2019) | 최신 | **Design Factors** 도입, **Performance Management** 현대화, 40개 목표로 확대 |

### COBIT 5 → COBIT 2019 핵심 변화

| 영역 | COBIT 5 | COBIT 2019 |
|------|---------|-----------|
| 프로세스 수 | 37개 | **40개** (신규 3개 추가) |
| 원칙 수 | 5개 | **6 거버넌스 시스템 + 3 거버넌스 프레임워크** |
| 조정 방식 | 일률적 | **11 Design Factors**로 기업별 맞춤 |
| 성과 측정 | Process Capability (0~5) | **CPM** (COBIT Performance Management) — 도메인별 유연 측정 |
| Focus Area | 없음 | **주제별 가이드** (SMB, 보안, 리스크, DevOps 등) |

---

## 3. COBIT 2019의 핵심 특징

### (1) 거버넌스 시스템(Governance System) 개념

COBIT 2019는 조직의 IT 거버넌스를 **하나의 통합 시스템**으로 본다:

```
           ┌──────────────────────────────┐
           │  Stakeholder Needs & Drivers │
           └───────────────┬──────────────┘
                           │
                           ▼
           ┌──────────────────────────────┐
           │     Enterprise Goals         │
           └───────────────┬──────────────┘
                           │
                           ▼
           ┌──────────────────────────────┐
           │   Alignment Goals (I&T)      │ ← 기존 "IT Goals"에서 개명
           └───────────────┬──────────────┘
                           │
                           ▼
           ┌──────────────────────────────┐
           │  Governance & Management     │
           │   Objectives (40개)          │
           └──────────────────────────────┘
```

### (2) 맞춤화(Tailoring) 가능

11개 **Design Factors**(기업 전략·목표·리스크 프로파일·규제 요건 등)에 따라 **40개 목표의 중요도 가중치가 달라짐**.

→ 예: 금융 기업은 **APO13 Security, MEA03 Compliance**가 중요, 스타트업은 **APO08 Relationships, BAI03 Solutions Identification**이 중요.

### (3) 7가지 거버넌스 컴포넌트

기존 "Enabler" 개념이 7개 **Components**로 재정의:

| Component | 의미 |
|-----------|------|
| Processes | 프로세스 |
| Organizational Structures | 조직 구조 |
| Information Flows & Items | 정보 흐름·항목 |
| People, Skills & Competencies | 인력·스킬·역량 |
| Culture, Ethics & Behavior | 문화·윤리·행동 |
| Policies & Procedures | 정책·절차 |
| Services, Infrastructure & Applications | 서비스·인프라·애플리케이션 |

→ 거버넌스는 **프로세스만이 아니라 조직·사람·문화의 총합**으로 접근.

---

## 4. COBIT의 6가지 거버넌스 시스템 원칙

COBIT 2019가 제시하는 **거버넌스 시스템이 따라야 할 6가지 원칙**:

| # | 원칙 | 의미 |
|---|------|------|
| 1 | **Provide Stakeholder Value** | 이해관계자 가치 제공 |
| 2 | **Holistic Approach** | 통합적 접근 (7 Components 동시 고려) |
| 3 | **Dynamic Governance System** | 동적 거버넌스 (변화에 지속 적응) |
| 4 | **Governance Distinct from Management** | **거버넌스와 관리의 명확한 분리** |
| 5 | **Tailored to Enterprise Needs** | 기업별 맞춤화 (Design Factors) |
| 6 | **End-to-End Governance System** | 전 범위 거버넌스 (IT 부서에 국한 X) |

### 추가: 3가지 거버넌스 프레임워크 원칙

| # | 원칙 | 의미 |
|---|------|------|
| 1 | Based on Conceptual Model | 개념 모델 기반 |
| 2 | Open and Flexible | 개방·유연 |
| 3 | Aligned to Major Standards | 주요 표준(ITIL·ISO·NIST 등)과 정렬 |

---

## 5. 왜 기업은 COBIT을 채택하는가

### (1) 규제 준수 요구

- **SOX (Sarbanes-Oxley)** — IT 통제 증명 요구
- **BASEL**, **Solvency II** — 금융 리스크 관리
- **GDPR**, **개인정보보호법** — 데이터 거버넌스
- **ISO/IEC 27001** — 정보보안 경영 시스템

→ COBIT은 이들 규제 요구를 **체계적으로 매핑**할 수 있는 참조 프레임워크.

### (2) IT 투자 가치 증명

- "IT가 비즈니스에 기여하는지" 이사회에 증명해야 하는 CIO·CFO의 요구
- COBIT의 **Goals Cascade**(이해관계자 → 기업 목표 → IT 목표 → 목표별 프로세스)가 근거 제공

### (3) IT 리스크 관리

- 사이버 공격·시스템 장애·컴플라이언스 위반의 리스크를 **통제 가능한 형태로 구조화**
- APO12 Managed Risk, APO13 Managed Security가 전담 목표

### (4) 감사 대응

- 내부 감사·외부 감사·규제 감사에서 **통제 성숙도** 증명 가능
- Capability Levels 0~5로 정량 평가

### (5) 다른 프레임워크와의 통합

- ITIL, ISO 20000, COSO, NIST CSF, TOGAF 등과 **매핑 가능**
- 단일 거버넌스 "우산"으로 복수 프레임워크 통합 운영

---

## 6. 적용 대상

| 조직 유형 | COBIT 활용 수준 |
|----------|---------------|
| **대기업·금융·공공** | 높음 (감사·규제 대응 필수) |
| **중견기업** | 중간 (맞춤형 적용, SMB Focus Area 참고) |
| **스타트업** | 낮음~중간 (Design Factor로 최소 범위 적용) |
| **IT 감사 법인** | 높음 (감사 기준 프레임워크) |
| **컨설팅** | 높음 (거버넌스 진단·설계) |

### 특히 COBIT이 필수인 산업

- **금융** — Basel, SOX, FFIEC 대응
- **공공·국방** — 국가 감사, 공공기관 경영평가
- **의료** — HIPAA, 의료 데이터 거버넌스
- **통신** — 전기통신사업법·네트워크 안정성 규제

---

## 한 줄 요약

**COBIT은 ISACA의 엔터프라이즈 IT 거버넌스 프레임워크**로, 현재 버전은 **COBIT 2019**. 40개 목표·5개 도메인·11 Design Factors를 통해 **비즈니스 목표와 IT를 정렬**하고, 감사·규제·리스크 관리의 기준선을 제공한다. ITIL이 "어떻게 운영하나(Management)"라면 COBIT은 **"무엇을 감독하나(Governance)"**에 특화.

---

## 관련 문서

- [COBIT 거버넌스 vs 관리](02-governance-vs-management.md)
- [COBIT 프레임워크 구조 (5 도메인·40 목표)](03-framework-structure.md)
- [COBIT Design Factors](04-design-factors.md)
- [COBIT Performance Management](05-performance-management.md)
- [ITIL vs COBIT 비교](06-itil-vs-cobit.md)
- [Governance vs Management (핵심 개념)](../key_concept/governance_vs_management.md)
