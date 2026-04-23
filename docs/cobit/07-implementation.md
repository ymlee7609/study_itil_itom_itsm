# COBIT 도입 가이드

COBIT은 **"도입 프로젝트"가 아니라 "거버넌스 체계의 점진적 성숙"**이다. 한 번에 40개 목표를 구현하려는 접근은 실패하며, **Design Factors 기반 우선순위 + 단계적 Capability Level 상승**이 정석이다.

## 목차

- [1. 도입 7단계 (COBIT 공식 모델)](#1-도입-7단계-cobit-공식-모델)
- [2. 실전 로드맵 예시](#2-실전-로드맵-예시)
- [3. 성공 요인과 실패 요인](#3-성공-요인과-실패-요인)
- [4. 첫 6개월에 해야 할 일](#4-첫-6개월에-해야-할-일)
- [5. 도입 후 운영 체계](#5-도입-후-운영-체계)
- [6. 인증과 교육](#6-인증과-교육)

---

## 1. 도입 7단계 (COBIT 공식 모델)

COBIT 2019 Implementation Guide의 **Continual Improvement Lifecycle**:

```
       1. What are the drivers?
              │
              ▼
       2. Where are we now?
              │
              ▼
       3. Where do we want to be?
              │
              ▼
       4. What needs to be done?
              │
              ▼
       5. How do we get there?
              │
              ▼
       6. Did we get there?
              │
              ▼
       7. How do we keep the momentum?
              │
              └───► (다시 1번으로, Continual)
```

### 각 단계 세부

| 단계 | 핵심 질문 | 산출물 |
|------|----------|-------|
| **1. Drivers** | 왜 거버넌스를 개선해야 하나? | Pain Points, Trigger Events |
| **2. Current State** | 현재 수준은? | Capability Level 진단 결과 |
| **3. Target State** | 목표 수준은? | Target Capability Level, Design Factor 기반 우선순위 |
| **4. What to do** | 어떤 개선이 필요한가? | Gap Analysis, 개선 항목 리스트 |
| **5. How to do** | 어떻게 달성할까? | 프로젝트 계획, BAI01 Program Management |
| **6. Did we** | 목표 달성했나? | 재진단 결과, Capability Level 비교 |
| **7. Momentum** | 지속 개선은? | KPI 대시보드, 정기 리뷰 체계 |

---

## 2. 실전 로드맵 예시

### 예시 1: 금융권 중견 기업 (3년 로드맵)

**초기 상태**:
- 기존 ITIL 일부 도입, 운영팀이 인시던트·변경 관리
- 감사 지적 누적 (MEA03, APO13 영역)
- 이사회의 IT 가시성 부족 (EDM 약함)

**Design Factor 분석 결과 우선순위 Top 10**:
APO13 Security, DSS05 Security Services, APO12 Risk, MEA03 Compliance, EDM03 Risk Optimization, DSS04 Continuity, APO09 SLA, BAI06 Changes, APO14 Data, DSS02 Incidents

**Year 1: 기초 체계**
| 분기 | 과제 |
|------|------|
| Q1 | COBIT Design Workshop, Capability 진단, 개선 계획 수립 |
| Q2 | EDM01 거버넌스 프레임워크 설정 (이사회 IT 위원회 설립) |
| Q3 | APO13 Security Policy 수립, MEA03 규제 매핑 |
| Q4 | APO12 Risk Register 구축 |

**Year 2: 운영 정착**
| 분기 | 과제 |
|------|------|
| Q1 | DSS05 Security 운영 자동화 (SIEM·SOAR) |
| Q2 | APO09 SLA 전면 재협상 |
| Q3 | DSS04 Continuity 테스트 정기화 |
| Q4 | APO14 Data Governance 착수 |

**Year 3: 성숙화**
| 분기 | 과제 |
|------|------|
| Q1 | MEA03 상시 컴플라이언스 자동화 |
| Q2 | BAI06 Standard Change 확대 + Guardrail |
| Q3 | EDM03 Risk KPI 이사회 대시보드 |
| Q4 | 전체 Focus Area Maturity Level 3 달성 |

### 예시 2: SMB (스타트업, 1년 경량 로드맵)

**Design Factor**: SMB, DevOps, First Mover, Cloud

**Focus Area**: SMB Focus Area 활용

**Year 1 단계**:
| 기간 | 과제 |
|------|------|
| M1~M3 | 핵심 10개 목표 식별 (APO04 Innovation, BAI03 Solutions, BAI06 Changes, DSS02 Incidents 등) |
| M4~M6 | 각 목표 Level 2 달성 (문서화·계획 수립) |
| M7~M9 | 핵심 목표 Level 3 (조직 표준화) |
| M10~M12 | Self-Assessment + 다음 연도 계획 |

---

## 3. 성공 요인과 실패 요인

### 성공 요인

| 요인 | 설명 |
|------|------|
| **이사회·CEO 참여** | EDM은 이사회 급 활동, 경영진 후원 없이 불가 |
| **작은 범위로 시작** | Design Factors로 10~15개 목표 선정, 한 번에 40개 X |
| **기존 체계 활용** | ITIL·ISO 있으면 그대로 매핑, 중복 구축 X |
| **정량 지표** | Capability Level로 진전 증명 |
| **변화 관리** | BAI05 Organizational Change 병행 |
| **교육** | COBIT 2019 Foundation 자격 취득자 확보 |

### 실패 요인

| 요인 | 증상 |
|------|------|
| **"프로젝트"로 접근** | 6개월 후 종료 → 성숙도 정체 |
| **모든 목표 동시 추진** | 리소스 분산, 어느 것도 Level 3 달성 못 함 |
| **IT팀 주도** | 이사회 참여 없어 EDM 형식화 |
| **문서만 작성** | 실제 활동 없이 감사 지적 대응용 |
| **ITIL 대체로 오해** | 기존 ITIL 폐기 후 COBIT만 → 실무 공백 |
| **Capability 무시** | Level 개념 없이 "COBIT 도입 완료" 선언 |

---

## 4. 첫 6개월에 해야 할 일

### Month 1: 준비

- [ ] COBIT 2019 Foundation 교육 (핵심 3~5명)
- [ ] Design Factor 워크숍 (이사회·경영진 포함)
- [ ] 기존 ITIL·ISO 성숙도 조사
- [ ] Sponsor 확보 (이사회 또는 CEO)

### Month 2: 진단

- [ ] Current Capability Level 자가 진단 (40개 전체)
- [ ] Pain Point 인터뷰
- [ ] 감사 지적·규제 요구 정리
- [ ] Gap 리포트 작성

### Month 3: 설계

- [ ] Design Factors 응답 완료
- [ ] Target Capability Level 설정
- [ ] 우선순위 10~15개 목표 확정
- [ ] 3년 로드맵 초안

### Month 4: 착수

- [ ] EDM01 거버넌스 프레임워크 공식화 (문서·위원회)
- [ ] Top 3 목표 개선 프로젝트 시작 (BAI01 Program)
- [ ] RACI 정의

### Month 5: 실행

- [ ] Top 3 목표 Level 2 → 3 작업
- [ ] ITIL·ISO와 매핑 문서화
- [ ] 중간 리포트 (이사회 보고)

### Month 6: 검증·확장

- [ ] Self-Assessment로 진전 확인
- [ ] 다음 Top 5 목표 추가 착수
- [ ] KPI 대시보드 v1
- [ ] 교훈 정리 → Year 2 계획

---

## 5. 도입 후 운영 체계

### 정기 거버넌스 리듬

| 주기 | 활동 | 대상 |
|------|------|------|
| **일간** | 운영 지표 (ITIL 중심) | 운영팀 |
| **주간** | 프로젝트·변경 상태 | 관리자 |
| **월간** | APO·MEA 목표 성과 | CIO |
| **분기** | **EDM 이사회 리뷰** (가치·리스크·자원) | **이사회** |
| **반기** | Capability Level 재진단 | 거버넌스 위원회 |
| **연간** | Design Factor 재검토, 로드맵 갱신 | 전사 |

### 거버넌스 조직 구성 (권장)

```
┌──────────────────────────────────┐
│        Board of Directors        │
│        (EDM 최종 책임)            │
└────────────────┬─────────────────┘
                 │
┌────────────────▼─────────────────┐
│   IT Steering Committee          │
│   (분기 EDM 리뷰, 투자 심의)       │
└─┬─────────────┬─────────────┬───┘
  │             │             │
┌─▼──────┐ ┌───▼────┐ ┌─────▼────┐
│ Risk   │ │ Audit  │ │ CIO/IT   │
│ Comm.  │ │ Comm.  │ │ Mgmt     │
└────────┘ └────────┘ └──────────┘
  EDM03      MEA04      APO·BAI·DSS
```

---

## 6. 인증과 교육

### 개인 인증

| 자격 | 대상 | 내용 |
|------|------|------|
| **COBIT 2019 Foundation** | 모든 실무자 | 프레임워크 기본 이해 |
| **COBIT 2019 Design and Implementation** | 거버넌스 설계자 | Design Factors 적용, 로드맵 수립 |
| **COBIT 2019 Assessor** | 감사·진단 전문가 | Capability Assessment 수행 |
| **CGEIT** (Certified in the Governance of Enterprise IT) | 임원·CIO 급 | IT 거버넌스 최상위 자격 (ISACA) |
| **CISA** (Certified Information Systems Auditor) | IT 감사인 | COBIT 기반 감사 |

### 관련 교육 과정

- ISACA 공식 교육 (온라인/오프라인)
- APMG-International 인증 트레이닝
- PeopleCert (ITIL과 통합 학습 권장)

### 국내 도입 리소스

- ISACA Korea Chapter (한국지부) — 정기 세미나
- 금융보안원·개인정보보호위원회 가이드 (COBIT 기반)
- 행정안전부 공공기관 정보보호 수준진단 (COBIT 참고)

---

## 체크리스트: 우리 조직은 COBIT이 필요한가?

**즉시 도입 필요 (아래 3개 이상 해당 시)**:
- [ ] SOX, Basel, 금감원 등 강한 외부 규제 적용
- [ ] IT 감사 지적이 반복적으로 발생
- [ ] 이사회가 IT 가시성 부족을 지적
- [ ] 주요 사이버 보안 사고 경험
- [ ] M&A·IPO 추진 중 (실사 대응)

**검토 필요 (1~2개 해당)**:
- [ ] IT 투자 가치 증명 압박
- [ ] 복수 프레임워크(ITIL·ISO)의 통합 필요
- [ ] 공공기관 경영평가 대상

**당장은 불필요 (해당 없음)**:
- [ ] 위 항목 모두 해당 없음 → ITIL 정착 후 재검토

---

## 한 줄 요약

**COBIT 도입은 한 번의 프로젝트가 아니라 3년 이상의 점진적 성숙 여정**이다. Design Factors로 10~15개 우선순위 목표를 선정하고, 이사회 후원·기존 ITIL/ISO 활용·정량 Capability Level 측정이 성공 3대 요소. 첫 6개월에 거버넌스 프레임워크(EDM01)와 Top 3 목표 Level 3 도달이 현실적 목표다.

---

## 관련 문서

- [COBIT 개요](01-overview.md)
- [COBIT Design Factors](04-design-factors.md)
- [COBIT Performance Management](05-performance-management.md)
- [ITIL vs COBIT 비교](06-itil-vs-cobit.md)
- [ITSM 모범 사례](../itsm/06-best-practices.md)
