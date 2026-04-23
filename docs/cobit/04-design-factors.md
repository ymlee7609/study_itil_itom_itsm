# COBIT Design Factors

COBIT 2019의 **가장 큰 혁신**. 모든 조직이 40개 목표를 동일한 우선순위로 다루는 것이 비현실적임을 인정하고, **11개 Design Factors**를 통해 **조직별 맞춤 거버넌스 시스템**을 설계하도록 한다.

## 목차

- [1. Design Factors가 왜 필요한가](#1-design-factors가-왜-필요한가)
- [2. 11개 Design Factors 전체](#2-11개-design-factors-전체)
- [3. 각 Design Factor 상세](#3-각-design-factor-상세)
- [4. 설계 프로세스 (Design Workflow)](#4-설계-프로세스-design-workflow)
- [5. 실무 예시](#5-실무-예시)
- [6. Focus Areas 연계](#6-focus-areas-연계)

---

## 1. Design Factors가 왜 필요한가

### 기존 문제

COBIT 5까지는 "모든 조직은 37개 프로세스를 모두 구현해야 한다"는 암묵적 전제가 있었다. 현실:
- 대기업은 40개 전부 관리 가능
- 중소기업은 10~15개도 과도한 부담
- 금융권은 보안·리스크 목표가 핵심
- 스타트업은 혁신·포트폴리오 목표가 핵심

→ 프레임워크가 **"모든 조직에 동일 적용"** 원칙으로는 확산·실효성 제한.

### COBIT 2019의 해법

```
           11 Design Factors 입력
                  │
                  ▼
         ┌──────────────────┐
         │  Design Workflow │
         └────────┬─────────┘
                  │
                  ▼
     ┌───────────────────────┐
     │  맞춤화된 거버넌스 시스템  │
     │  - 40 목표의 우선순위    │
     │  - Capability Level 목표 │
     │  - Focus Area 선택        │
     └───────────────────────┘
```

**원리**: 11개 요소에 대한 조직의 응답을 바탕으로 **각 목표의 중요도 점수**가 산출되고, 우선순위가 자동 조정된다.

---

## 2. 11개 Design Factors 전체

| # | Design Factor | 의미 |
|---|--------------|------|
| **DF1** | Enterprise Strategy | 기업 전략 (성장·혁신·안정 등) |
| **DF2** | Enterprise Goals | 기업 목표 (재무·고객·내부·학습) |
| **DF3** | Risk Profile | 리스크 프로파일 (감수·회피 성향) |
| **DF4** | I&T-Related Issues | 현재 IT 이슈 (20개 사전 정의 항목) |
| **DF5** | Threat Landscape | 위협 환경 (일반·높음) |
| **DF6** | Compliance Requirements | 규제 준수 수준 (낮음·일반·높음) |
| **DF7** | Role of IT | IT의 역할 (Support·Factory·Turnaround·Strategic) |
| **DF8** | Sourcing Model for IT | 소싱 모델 (Insourced·Outsourced·Hybrid·Cloud) |
| **DF9** | IT Implementation Methods | 구현 방법 (Agile·DevOps·Traditional·Hybrid) |
| **DF10** | Technology Adoption Strategy | 기술 도입 (First Mover·Follower·Slow Adopter) |
| **DF11** | Enterprise Size | 기업 규모 (Large·SMB) |

---

## 3. 각 Design Factor 상세

### DF1: Enterprise Strategy

조직이 추구하는 전략 유형 (선택 1개 또는 가중치):

| 전략 | 설명 | 영향 |
|------|------|------|
| **Growth/Acquisition** | 성장·인수합병 | APO05 포트폴리오, BAI01 프로그램 중요 |
| **Innovation/Differentiation** | 혁신·차별화 | APO04 혁신 중요 |
| **Cost Leadership** | 원가 우위 | APO06 예산·원가 중요 |
| **Client Service/Stability** | 서비스·안정 | DSS01 운영, APO09 SLA 중요 |

### DF2: Enterprise Goals

BSC(Balanced Scorecard) 4개 관점에 따른 **13개 기업 목표**:

| 관점 | 목표 예 |
|------|---------|
| Financial | Portfolio of competitive products, Managed financial risks |
| Customer | Customer-oriented service culture, Continuity of services |
| Internal | Optimization of business processes, Operational excellence |
| Learning | Staff skills and motivation, Innovation capability |

각 목표의 **중요도**(Not Important → Very Important)를 선택하면 COBIT이 자동으로 연관 IT 목표·COBIT 목표에 가중치를 전파한다.

### DF3: Risk Profile

18개 사전 정의된 IT 리스크 카테고리별 **발생 빈도 × 영향도**를 평가:

예시 리스크:
- IT operations incidents
- Information security / Cyberattacks
- Regulatory compliance
- Technology-based innovation
- Software implementation / adoption
- IT service provider failure

→ 리스크가 높은 항목의 대응 목표(APO12, APO13, DSS05 등)가 상향됨.

### DF4: I&T-Related Issues

20개 사전 정의된 IT 이슈 중 해당 여부 선택:

- Frustration between IT and business
- IT projects over budget/time
- Duplicated solutions
- Regulatory non-compliance
- Security breaches
- Legacy systems
- ... 등

### DF5: Threat Landscape

- **Normal**: 일반 수준의 위협 환경
- **High**: 높은 수준 (국가 핵심 인프라, 금융 등)

### DF6: Compliance Requirements

- **Low**: 낮은 규제
- **Normal**: 일반
- **High**: 강한 규제 (금융, 의료, 공공, 방산)

### DF7: Role of IT

조직 내 IT의 **비즈니스 역할**:

| 역할 | 특징 |
|------|------|
| **Support** | 백오피스 지원 (예: 소매업 IT) |
| **Factory** | 핵심 인프라 (예: 제조업) |
| **Turnaround** | 전환기에 IT 역할 급성장 중 |
| **Strategic** | IT가 비즈니스 본질 (예: 은행, 플랫폼 기업) |

→ Strategic 조직은 40개 목표 거의 전부 고성숙도 요구.

### DF8: Sourcing Model

| 모델 | 특징 |
|------|------|
| **Insourced** | 자체 운영 |
| **Outsourced** | 외주 |
| **Hybrid** | 혼합 |
| **Cloud** | 클라우드 중심 |

→ Outsourced/Cloud는 **APO10 Vendor Management**가 중요도 급상승.

### DF9: IT Implementation Methods

- **Traditional** (Waterfall)
- **Agile**
- **DevOps**
- **Hybrid**

→ DevOps는 BAI06(Change) 자동화, DSS01(Operations) 실시간화 요구.

### DF10: Technology Adoption Strategy

- **First Mover**: 최신 기술 조기 도입
- **Follower**: 성숙 기술 도입
- **Slow Adopter**: 검증된 기술만

→ First Mover는 APO04(Innovation)이 필수.

### DF11: Enterprise Size

- **Large**: 대기업
- **Small and Medium (SMB)**: 중소기업 → COBIT 2019 **SMB Focus Area** 활용

---

## 4. 설계 프로세스 (Design Workflow)

COBIT 2019는 5단계 설계 워크플로우를 제시한다:

```
Step 1: Understand Enterprise Context
   ↓
Step 2: Determine Initial Scope (DF 1-4 기반)
   ↓
Step 3: Refine Scope (DF 5-11 기반)
   ↓
Step 4: Conclude the Design
   ↓
Step 5: Launch & Iterate
```

### Step 1: Understand Context

- 기업 전략·목표 이해
- 이해관계자 식별
- 현재 거버넌스 실태 진단

### Step 2: Initial Scope

- DF1~DF4 입력 → 40개 목표의 **초기 중요도** 산출
- 산출물: Preliminary Governance System Scope

### Step 3: Refine Scope

- DF5~DF11 입력 → 중요도 조정
- Threat Landscape·Compliance가 높으면 보안·MEA03 목표 상향
- Cloud 소싱이면 APO10 벤더 관리 상향

### Step 4: Conclude Design

- 최종 **우선순위 목표 리스트** 확정
- 각 목표의 **Target Capability Level** 설정 (0~5)
- Focus Area 선택 (Security, Risk, DevOps, SMB 등)

### Step 5: Launch

- 도입 로드맵 수립 (BAI01 Program Management와 연계)
- 성과 측정 (CPM 적용)

---

## 5. 실무 예시

### 예시 1: 국내 금융권 기업

| Design Factor | 응답 |
|--------------|------|
| DF1 Strategy | Client Service/Stability |
| DF3 Risk Profile | Cyberattack High, Compliance High |
| DF6 Compliance | **High** (금감원, 개인정보보호법, 전자금융거래법) |
| DF7 Role of IT | **Strategic** |
| DF9 Methods | Hybrid (Traditional + Agile) |

**산출 우선순위 (상위 10개)**:
1. APO13 Security
2. DSS05 Security Services
3. APO12 Risk
4. MEA03 External Compliance
5. EDM03 Risk Optimization
6. DSS04 Continuity
7. APO09 Service Agreements
8. BAI06 IT Changes
9. APO14 Data
10. DSS02 Incidents

### 예시 2: 스타트업 (SaaS)

| Design Factor | 응답 |
|--------------|------|
| DF1 Strategy | Innovation/Differentiation |
| DF7 Role of IT | Strategic |
| DF9 Methods | **DevOps** |
| DF10 Adoption | **First Mover** |
| DF11 Size | SMB |

**산출 우선순위 (상위 10개)**:
1. APO04 Innovation
2. BAI03 Solutions Identification
3. BAI06 IT Changes (DevOps 자동화)
4. APO02 Strategy
5. DSS01 Operations
6. APO08 Relationships
7. BAI11 Projects
8. APO05 Portfolio
9. DSS02 Incidents
10. BAI08 Knowledge

### 예시 3: 공공기관

| Design Factor | 응답 |
|--------------|------|
| DF6 Compliance | **High** (감사원, 공공기관 경영평가) |
| DF7 Role of IT | Support/Factory |
| DF8 Sourcing | **Outsourced** (SI 업체) |

**산출 우선순위 (상위 10개)**:
1. MEA03 External Compliance
2. APO10 Vendor Management
3. MEA02 Internal Control
4. MEA04 Assurance
5. EDM01 Governance Framework
6. APO09 Service Agreements
7. APO13 Security
8. EDM03 Risk Optimization
9. DSS05 Security
10. APO06 Budget and Costs

---

## 6. Focus Areas 연계

COBIT 2019는 특정 주제에 대한 **별도 Focus Area 가이드**를 제공한다:

| Focus Area | 대상 |
|-----------|------|
| **Information Security** | CISO, 보안 담당 |
| **Risk** | 리스크 관리자 |
| **DevOps** | DevOps 팀 |
| **SMB (Small and Medium Business)** | 중소기업 |
| **COBIT Design Guide** | 거버넌스 설계자 |
| **Implementation Guide** | 도입 담당 |

각 Focus Area는 **관련 목표의 우선순위·실행 가이드·측정 방법**을 구체화한다.

### 예: DevOps Focus Area

- 중점 목표: BAI06 (변경), BAI07 (전환), DSS01 (운영), DSS02 (인시던트)
- CI/CD 파이프라인 관점 재해석
- Error Budget, SRE 개념 연결
- ITIL 4 / DASA DevOps 프레임워크 매핑

---

## 한 줄 요약

**11개 Design Factors**(전략·목표·리스크·이슈·위협·규제·IT역할·소싱·구현방식·기술도입·규모)를 조직에 적용하면 COBIT이 **40개 목표의 우선순위**를 자동 산출한다. 이것이 COBIT 2019의 차별화 핵심이며, **"모든 조직이 똑같이 구현"**에서 **"조직별 맞춤 거버넌스"**로의 전환을 가능케 한다.

---

## 관련 문서

- [COBIT 개요](01-overview.md)
- [COBIT 프레임워크 구조](03-framework-structure.md)
- [COBIT Performance Management](05-performance-management.md)
- [COBIT 도입 가이드](07-implementation.md)
