# COBIT 프레임워크 구조 (5 도메인·40 목표)

COBIT 2019의 핵심 본체. **5개 도메인**에 **40개 거버넌스·관리 목표**가 배치되어 있다. 각 목표는 **프로세스·산출물·지표·성숙도**를 포함하는 **거버넌스 단위**다.

## 목차

- [1. 전체 구조 한눈에](#1-전체-구조-한눈에)
- [2. EDM — 거버넌스 도메인 (5개 목표)](#2-edm--거버넌스-도메인-5개-목표)
- [3. APO — 정렬·계획·조직 (14개 목표)](#3-apo--정렬계획조직-14개-목표)
- [4. BAI — 구축·획득·구현 (11개 목표)](#4-bai--구축획득구현-11개-목표)
- [5. DSS — 전달·서비스·지원 (6개 목표)](#5-dss--전달서비스지원-6개-목표)
- [6. MEA — 모니터링·평가·진단 (4개 목표)](#6-mea--모니터링평가진단-4개-목표)
- [7. 목표별 구성 요소](#7-목표별-구성-요소)

---

## 1. 전체 구조 한눈에

```
                    COBIT 2019
                     40 목표
                        │
        ┌───────────────┼───────────────────┐
        │                                   │
   Governance                          Management
   (5 목표)                             (35 목표)
        │                                   │
       EDM                ┌──────┬──────┬──────┐
    (5 목표)             APO    BAI    DSS    MEA
                       (14)   (11)    (6)    (4)
                        │      │      │      │
                       계획   구축   운영   측정
```

### 도메인 요약표

| 도메인 | 코드 | 영역 | 목표 수 | 주요 키워드 |
|--------|------|------|---------|------------|
| Evaluate, Direct, Monitor | **EDM** | 거버넌스 | 5 | 전략·리스크 수용·가치·자원·이해관계자 |
| Align, Plan, Organize | **APO** | 정렬·계획 | 14 | IT 전략·아키텍처·조직·인력·리스크·보안·벤더 |
| Build, Acquire, Implement | **BAI** | 구축 | 11 | 프로그램·요구사항·솔루션·변경·프로젝트 |
| Deliver, Service, Support | **DSS** | 운영 | 6 | 운영·요청·문제·연속성·보안·통제 |
| Monitor, Evaluate, Assess | **MEA** | 감사 | 4 | 성과·내부통제·외부요구사항·감사 |

---

## 2. EDM — 거버넌스 도메인 (5개 목표)

이사회·거버넌스 바디가 **Evaluate·Direct·Monitor** 하는 영역.

| 코드 | 목표명 | 핵심 질문 |
|------|--------|----------|
| **EDM01** | Ensured Governance Framework Setting and Maintenance | 거버넌스 프레임워크 자체가 세팅·유지되나? |
| **EDM02** | Ensured Benefits Delivery | IT 투자가 실제 **가치**를 창출하나? |
| **EDM03** | Ensured Risk Optimization | 리스크 수용 한도·프로파일이 최적인가? |
| **EDM04** | Ensured Resource Optimization | IT 자원이 최적 활용되나? |
| **EDM05** | Ensured Stakeholder Engagement | 이해관계자와의 투명한 소통이 유지되나? |

### EDM 목표의 역할 매트릭스

| 이슈 | 담당 EDM 목표 |
|------|--------------|
| 이사회 IT 정책 부재 | EDM01 |
| IT 투자 ROI 논란 | EDM02 |
| 사이버 보험 가입 여부 | EDM03 |
| IT 인력 과잉·부족 | EDM04 |
| 주주·규제기관 커뮤니케이션 | EDM05 |

---

## 3. APO — 정렬·계획·조직 (14개 목표)

**전략 수립과 조직 구성** 영역. CIO·IT 전략기획 담당의 핵심 영역.

| 코드 | 목표명 | 요점 |
|------|--------|------|
| **APO01** | Managed I&T Management Framework | IT 관리 프레임워크 자체 관리 |
| **APO02** | Managed Strategy | IT 전략 |
| **APO03** | Managed Enterprise Architecture | 엔터프라이즈 아키텍처 |
| **APO04** | Managed Innovation | 혁신 |
| **APO05** | Managed Portfolio | IT 포트폴리오 |
| **APO06** | Managed Budget and Costs | 예산·원가 |
| **APO07** | Managed Human Resources | 인적 자원 |
| **APO08** | Managed Relationships | 비즈니스 관계 |
| **APO09** | Managed Service Agreements | **SLA** 관리 |
| **APO10** | Managed Vendors | 벤더 관리 |
| **APO11** | Managed Quality | 품질 |
| **APO12** | Managed Risk | **IT 리스크** |
| **APO13** | Managed Security | **보안** |
| **APO14** | Managed Data | **데이터 관리** (COBIT 2019 신규) |

### APO 도메인의 중요 목표

- **APO12 Risk** + **APO13 Security** = 사이버 보안 거버넌스 양대 축
- **APO09 Service Agreements** ↔ ITIL의 SLA 관리와 직접 대응
- **APO10 Vendors** ↔ ITIL의 Supplier Management
- **APO14 Data** — COBIT 2019에 신규 추가, 데이터 거버넌스 대응

---

## 4. BAI — 구축·획득·구현 (11개 목표)

**신규 솔루션을 만들고 도입**하는 영역. 프로젝트·변경·구현의 축.

| 코드 | 목표명 | 요점 |
|------|--------|------|
| **BAI01** | Managed Programs | 프로그램 관리 |
| **BAI02** | Managed Requirements Definition | 요구사항 정의 |
| **BAI03** | Managed Solutions Identification and Build | 솔루션 식별·구축 |
| **BAI04** | Managed Availability and Capacity | **가용성·용량** (신규 2019) |
| **BAI05** | Managed Organizational Change | **조직 변화 관리** |
| **BAI06** | Managed IT Changes | **IT 변경 관리** (ITIL Change와 대응) |
| **BAI07** | Managed IT Change Acceptance and Transitioning | 변경 수용·전환 |
| **BAI08** | Managed Knowledge | 지식 관리 |
| **BAI09** | Managed Assets | **자산 관리** (ITAM과 대응) |
| **BAI10** | Managed Configuration | **구성 관리** (CMDB와 대응) |
| **BAI11** | Managed Projects | 프로젝트 관리 |

### BAI 목표의 ITIL 대응

| BAI 목표 | ITIL 대응 프랙티스 |
|----------|-------------------|
| BAI04 | Availability Management, Capacity Management |
| BAI06 | Change Enablement |
| BAI07 | Release Management, Deployment Management |
| BAI08 | Knowledge Management |
| BAI09 | IT Asset Management |
| BAI10 | Service Configuration Management |
| BAI11 | Project Management |

---

## 5. DSS — 전달·서비스·지원 (6개 목표)

**운영 영역**. ITIL이 가장 강한 영역과 겹치며, COBIT은 통제 관점에서 접근.

| 코드 | 목표명 | 요점 |
|------|--------|------|
| **DSS01** | Managed Operations | 운영 관리 |
| **DSS02** | Managed Service Requests and Incidents | **서비스 요청·인시던트** |
| **DSS03** | Managed Problems | **문제 관리** |
| **DSS04** | Managed Continuity | **연속성** (BCM/DR) |
| **DSS05** | Managed Security Services | **보안 운영** |
| **DSS06** | Managed Business Process Controls | 비즈니스 프로세스 통제 |

### DSS 목표의 ITIL 대응

- **DSS02** = ITIL Incident Management + Service Request Management
- **DSS03** = ITIL Problem Management
- **DSS04** = ITIL Service Continuity Management
- **DSS05** = ITIL Information Security Management (운영 측면)

---

## 6. MEA — 모니터링·평가·진단 (4개 목표)

**감사와 성과 측정** 영역. 통제 루프를 닫는 역할.

| 코드 | 목표명 | 요점 |
|------|--------|------|
| **MEA01** | Managed Performance and Conformance Monitoring | 성과·준수 모니터링 |
| **MEA02** | Managed System of Internal Control | 내부 통제 시스템 |
| **MEA03** | Managed Compliance with External Requirements | **외부 규제 준수** |
| **MEA04** | Managed Assurance | **보증·감사** |

### MEA의 중요성

- **MEA03** — GDPR, SOX, Basel 등 **외부 규제 대응**의 중심
- **MEA04** — 내부 감사·외부 감사 품질 보증
- 많은 조직이 MEA를 소홀히 하여 **규제 위반·감사 실패** 발생

---

## 7. 목표별 구성 요소

각 40개 목표는 **표준화된 구조**로 기술된다:

```
┌─────────────────────────────────────────────────┐
│  [목표 코드] [목표명]                              │
├─────────────────────────────────────────────────┤
│  Description (서술)                              │
│  Purpose (목적)                                  │
├─────────────────────────────────────────────────┤
│  Governance/Management Practices (관행)          │
│  (EDM01.01, EDM01.02, ... 형태)                 │
├─────────────────────────────────────────────────┤
│  Activities (활동)                              │
│  Inputs / Outputs (입력 / 산출물)                │
│  Roles (RACI)                                    │
├─────────────────────────────────────────────────┤
│  Related Guidance (관련 표준: ITIL, ISO 등)     │
├─────────────────────────────────────────────────┤
│  Component Guidance:                             │
│   - Processes                                    │
│   - Organizational Structures                    │
│   - Information Flows                            │
│   - People/Skills                                │
│   - Culture/Ethics                               │
│   - Policies                                     │
│   - Services/Infrastructure                      │
└─────────────────────────────────────────────────┘
```

### 예: DSS02 (Service Requests & Incidents) 구조

| 항목 | 내용 |
|------|------|
| **Purpose** | 사용자 생산성 향상, 서비스 중단 최소화 |
| **Practices** | DSS02.01 서비스 요청·인시던트 분류 스킴 정의, DSS02.02 기록·분류·우선순위 지정, ... (총 7개 관행) |
| **Key Activities** | 티켓 접수, 분류, 에스컬레이션, 해결, 종결 |
| **RACI** | R/A: Service Desk Manager / C: Process Owner / I: Business Owner |
| **Related Guidance** | ITIL 4 Incident Management, ISO 20000 |
| **Metrics** | First-call Resolution Rate, MTTR, SLA 준수율 |

---

## 한 줄 요약

**COBIT 2019는 40개 목표를 5개 도메인(EDM·APO·BAI·DSS·MEA)에 배치**한다. EDM(5개)은 거버넌스, APO/BAI/DSS/MEA(35개)는 관리를 담당하며, 각 목표는 관행·활동·RACI·관련 표준이 포함된 **표준화된 구조**로 정의된다. ITIL·ISO와의 매핑이 명시되어 통합 운영의 기반이 된다.

---

## 관련 문서

- [COBIT 개요](01-overview.md)
- [COBIT 거버넌스 vs 관리](02-governance-vs-management.md)
- [COBIT Design Factors](04-design-factors.md)
- [COBIT Performance Management](05-performance-management.md)
- [ITIL vs COBIT 비교](06-itil-vs-cobit.md)
