# COBIT Performance Management (CPM)

COBIT 2019의 **두 번째 혁신**. COBIT 5의 Process Capability Model(PCM)을 대체한 **CPM**(COBIT Performance Management)은 **성숙도 측정**을 이원화해 도메인별 현실을 반영한다.

## 목차

- [1. CPM의 도입 배경](#1-cpm의-도입-배경)
- [2. Capability Levels 0~5](#2-capability-levels-05)
- [3. Maturity Levels (조직 전체)](#3-maturity-levels-조직-전체)
- [4. Capability vs Maturity](#4-capability-vs-maturity)
- [5. 측정 실무](#5-측정-실무)
- [6. Component별 Capability 구성](#6-component별-capability-구성)

---

## 1. CPM의 도입 배경

### COBIT 5 시절의 한계

COBIT 5는 ISO/IEC 15504 기반 **Process Capability Assessment**를 사용:
- 너무 엄격 (대규모 감사 팀 필요)
- 측정 대상이 **프로세스**에 국한 (Component 전체 반영 못 함)
- 조직 규모·성격 무관하게 동일 기준 적용

### COBIT 2019의 CPM

- **2단계 측정**: Capability(개별 목표) + Maturity(조직 전체)
- **Component 전반** 반영 (프로세스 + 조직·인력·문화 등 7개)
- **Focus Area별 기준 조정** 가능
- **Self-Assessment** 가능한 구조 (경량 진단)

---

## 2. Capability Levels 0~5

각 **거버넌스·관리 목표(40개)**의 개별 성숙도를 0~5 레벨로 측정:

| Level | 이름 | 의미 |
|-------|------|------|
| **0** | Incomplete Process | 목표 미달성, 의도된 결과 없음 |
| **1** | Performed Process | 목표 **달성은 되지만 비공식적** |
| **2** | Managed Process | **관리됨** (계획·모니터링·문서화) |
| **3** | Established Process | **조직 표준**으로 확립 |
| **4** | Predictable Process | **정량적 측정·예측** 가능 |
| **5** | Optimizing Process | **지속 개선** 상시 수행 |

### 각 Level의 특징

```
Level 0 ─── Level 1 ─── Level 2 ─── Level 3 ─── Level 4 ─── Level 5
 ✗          ○           ⚙            📖           📊           🔄
Nothing   Ad-hoc      Managed     Standardized  Measured    Optimizing
```

| Level | 조직 모습 |
|-------|-----------|
| 0 | "그냥 안 함" 또는 "결과 없음" |
| 1 | "영웅적 개인이 해결" (속인화) |
| 2 | "계획하고 문서화하긴 함" |
| 3 | "전사 표준 프로세스로 운영" |
| 4 | "지표로 정량 관리·예측" |
| 5 | "피드백 루프·개선 문화" |

### 각 Level의 예시 (DSS02 Incident Management)

| Level | DSS02 실태 |
|-------|-----------|
| 0 | 인시던트 기록 없음, 장애 시 즉흥 대응 |
| 1 | 티켓은 만들지만 분류 없음, 해결 담당자 임의 지정 |
| 2 | 티켓 분류·우선순위 기준 있음, SLA 정의 |
| 3 | 전사 Incident Process 표준화, KEDB 활용 |
| 4 | MTTR·FCR 정량 측정, 월간 트렌드 분석 |
| 5 | Post-mortem 문화, Problem 연계로 재발 차단, 자동화 개선 상시 |

---

## 3. Maturity Levels (조직 전체)

개별 목표의 Capability Level을 **도메인 또는 Focus Area 단위로 집계**한 값.

### Focus Area별 Maturity 계산

특정 Focus Area의 Maturity Level 달성 조건:
- 해당 Focus Area에 속한 **핵심 목표들이 모두 동일 Capability Level 이상** 달성
- 일부 목표만 높고 일부 낮으면 낮은 쪽 기준

### 예: 정보 보안 Focus Area의 Maturity

정보 보안 Focus Area 핵심 목표: EDM03, APO12, APO13, DSS05, MEA03

| 목표 | Capability Level |
|------|------------------|
| EDM03 | 4 |
| APO12 | 3 |
| APO13 | 3 |
| DSS05 | 2 |
| MEA03 | 3 |

→ **보안 Maturity = 2** (가장 낮은 DSS05 기준)

즉, DSS05를 먼저 3으로 올려야 전체 Maturity가 3으로 올라감.

---

## 4. Capability vs Maturity

| 구분 | Capability Level | Maturity Level |
|------|------------------|----------------|
| **대상** | 개별 목표 (40개 각각) | Focus Area 또는 조직 전체 |
| **범위** | 좁음 (한 목표의 성숙도) | 넓음 (관련 목표 집합) |
| **용도** | 개선 우선순위 식별 | 거버넌스 전체 진단 |
| **의사결정** | "DSS02를 3으로" | "보안 Maturity를 3으로" |
| **산출** | 40개 수치 | 도메인·주제별 요약 수치 |

---

## 5. 측정 실무

### 측정 방법 3가지

| 방법 | 상세도 | 리소스 | 용도 |
|------|--------|--------|------|
| **Self-Assessment** | 중 | 낮음 | 내부 상시 진단 |
| **Light Assessment** | 중상 | 중 | 분기 진단 |
| **Formal Assessment** | 최고 | 높음 | 감사, 인증, 연 1회 |

### 측정 프로세스

```
1. 측정 대상 선정 (Design Factors 우선순위 기반)
   ↓
2. Level별 증거 수집
   - 문서 (정책, 절차, SOP)
   - 시스템 로그 (ITSM 티켓, 모니터링 데이터)
   - 인터뷰 (담당자, 이해관계자)
   ↓
3. Component 7개별 평가
   - Processes, Org Structures, Info Flows, People,
     Culture, Policies, Services/Infrastructure
   ↓
4. Capability Level 판정
   ↓
5. Gap 분석 → 개선 계획
```

### 측정 지표 (각 Level별 체크)

#### Level 1 → 2 상승 조건
- [ ] 목표가 계획되어 있음
- [ ] 진행 상황이 모니터링됨
- [ ] 결과가 조정·관리됨
- [ ] 문서화됨

#### Level 2 → 3 상승 조건
- [ ] 표준 프로세스가 정의됨
- [ ] 조직 전체에 일관되게 적용됨
- [ ] 프로세스 자산 라이브러리 존재
- [ ] 교육·지원 체계 있음

#### Level 3 → 4 상승 조건
- [ ] 정량적 목표 설정
- [ ] 정량적 측정 데이터 수집
- [ ] 통계적 분석
- [ ] 예측 가능성 확보

#### Level 4 → 5 상승 조건
- [ ] 정량 데이터 기반 개선 프로세스
- [ ] 혁신·최적화 체계
- [ ] 변화 관리 성숙도

---

## 6. Component별 Capability 구성

COBIT 2019는 Capability Level을 **단일 프로세스 측정이 아닌 7개 Component 종합**으로 본다:

### 각 Component의 Level 기여

| Component | Level 2 요건 | Level 3 요건 | Level 4 요건 |
|-----------|-------------|-------------|-------------|
| **Processes** | 문서화된 절차 | 조직 표준 | 정량 측정 |
| **Org Structures** | RACI 정의 | 전담 조직 | 성과 평가 체계 |
| **Info Flows** | 기본 보고 체계 | 표준 리포트 | 대시보드·KPI |
| **People/Skills** | 담당자 지정 | 교육 프로그램 | 역량 모델 |
| **Culture/Ethics** | 규칙 인지 | 행동 규범 | 문화 측정 |
| **Policies/Procedures** | 정책 문서 | 정책 생명주기 | 영향 분석 |
| **Services/Infra** | 기본 도구 | 표준 도구 | 자동화 |

### 평가 시 주의점

- 프로세스만 높은데 인력·문화가 뒤처지면 **Level 3 불가**
- 도구(Services/Infra)만 첨단이고 정책이 없으면 **Level 2도 미달**
- 7개 Component가 **균형적 성장**해야 Level 상승

---

## 실무 적용: 개선 로드맵 예시

### 현 상태 (기업 A — 제조업)

| 목표 | 현재 Level | Target Level (3년) |
|------|-----------|--------------------|
| APO12 Risk | 1 | **3** |
| APO13 Security | 2 | **3** |
| DSS02 Incidents | 3 | 3 (유지) |
| DSS05 Security | 2 | **3** |
| MEA03 Compliance | 1 | **3** |

### 연차별 투자 계획

| 연도 | 핵심 과제 |
|------|----------|
| Year 1 | APO13 → 3 (보안 정책 표준화), MEA03 → 2 (규제 매핑) |
| Year 2 | APO12 → 3 (리스크 관리 체계), DSS05 → 3 (보안 운영 자동화) |
| Year 3 | MEA03 → 3 (감사 대응 상시화), 전체 Focus Area Maturity 3 달성 |

→ **Capability Level은 3년 이상의 로드맵**. 한 번에 5로 가는 것 불가능.

---

## 한 줄 요약

**CPM은 COBIT 2019의 성숙도 측정 체계**로, **Capability Level 0~5**(개별 목표)와 **Maturity Level**(Focus Area 단위)을 이원화해 운영한다. 7개 Component 균형 성장을 전제로 하며, Level 3(조직 표준)은 대부분의 기업이 현실적으로 목표로 삼는 수준이다.

---

## 관련 문서

- [COBIT 개요](01-overview.md)
- [COBIT 프레임워크 구조](03-framework-structure.md)
- [COBIT Design Factors](04-design-factors.md)
- [COBIT 도입 가이드](07-implementation.md)
- [KPI vs Metric vs CSF](../key_concept/kpi_vs_metric_vs_csf.md)
