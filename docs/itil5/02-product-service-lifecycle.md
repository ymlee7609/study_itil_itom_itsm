# ITIL 5 제품 및 서비스 라이프사이클 모델 (PSLM)

## 목차

- [1. 개요](#1-개요)
- [2. ITIL 4 서비스 가치 사슬과의 비교](#2-itil-4-서비스-가치-사슬과의-비교)
- [3. 8가지 활동 상세](#3-8가지-활동-상세)
- [4. PSLM의 핵심 특성](#4-pslm의-핵심-특성)
- [5. 실무 적용 시나리오](#5-실무-적용-시나리오)

---

## 1. 개요

**제품 및 서비스 라이프사이클 모델(Product and Service Lifecycle Model, PSLM)**은 ITIL 5의 핵심 모델이다. ITIL 4의 서비스 가치 사슬(Service Value Chain)을 대체하며, 디지털 제품과 서비스를 통합적으로 관리하는 라이프사이클을 제공한다.

PSLM은 ITIL 가치 시스템(ITIL Value System)에서 **ITIL Value Chain**이라고도 불린다.

### 핵심 철학

- 직선적이 아닌 **반복적(Iterative)** 모델
- 활동 간 자유로운 이동 가능 (현실 팀 운영 방식 반영)
- Agile, DevOps 방법론과 자연스럽게 통합
- 가치 공동 창출(Value Co-creation) 중심

---

## 2. ITIL 4 서비스 가치 사슬과의 비교

| 비교 항목 | ITIL 4 서비스 가치 사슬 (SVC) | ITIL 5 제품 및 서비스 라이프사이클 (PSLM) |
|----------|------------------------------|----------------------------------------|
| 활동 수 | 6개 | 8개 |
| 명칭 | Service Value Chain | ITIL Value Chain (in ITIL Value System) |
| 초점 | 서비스 가치 창출 | 디지털 제품 + 서비스 가치 창출 |
| 구조 | 비선형적이지만 서비스 중심 | 반복적, 제품 로드맵 중심 |
| 범위 | 서비스 관리 | 발견(Discover) ~ 지원(Support) 전체 포괄 |

### 활동 매핑

| ITIL 4 SVC | ITIL 5 PSLM |
|------------|-------------|
| Plan | Discover (탐색 + 계획 분리) |
| Engage | (Discover에 통합, 별도 관계 모델로 분리) |
| Design & Transition | Design + Transition (분리) |
| Obtain/Build | Acquire + Build (분리) |
| Deliver & Support | Deliver + Support (분리) |
| Improve | (전체 활동에 내재화) |
| - | Operate (신규 독립 활동) |

---

## 3. 8가지 활동 상세

### 3.1 Discover (발견)

| 항목 | 설명 |
|------|------|
| **목적** | 니즈와 기회를 식별하고 우선순위화 |
| **핵심 활동** | 시장 조사, 사용자 리서치, 니즈 분석, 제품 로드맵 정렬 |
| **입력** | 비즈니스 전략, 사용자 피드백, 시장 트렌드 |
| **출력** | 제품/서비스 기회 목록, 우선순위화된 백로그 |
| **관련 프랙티스** | Strategy Management, Portfolio Management, Business Analysis |

### 3.2 Design (설계)

| 항목 | 설명 |
|------|------|
| **목적** | 기술적 요구사항과 사용자 기대를 충족하는 솔루션 설계 |
| **핵심 활동** | 아키텍처 설계, UX 설계, 서비스 수준 설계, 보안 설계 |
| **입력** | 요구사항 정의, 기존 아키텍처, 제약 조건 |
| **출력** | 설계 문서, 서비스 수준 목표, 아키텍처 청사진 |
| **관련 프랙티스** | Service Design, Architecture Management, Information Security Management |

### 3.3 Acquire (획득)

| 항목 | 설명 |
|------|------|
| **목적** | 필요한 리소스와 구성 요소 확보 |
| **핵심 활동** | 벤더 선정, 라이선스 구매, 클라우드 인프라 프로비저닝, 인력 확보 |
| **입력** | 설계 문서, 예산, 벤더 목록 |
| **출력** | 확보된 리소스, 계약서, SLA |
| **관련 프랙티스** | Supplier Management, Service Financial Management |

### 3.4 Build (구축)

| 항목 | 설명 |
|------|------|
| **목적** | 솔루션 개발, 구성, 테스트 |
| **핵심 활동** | 소프트웨어 개발, 구성 관리, 통합 테스트, 품질 보증 |
| **입력** | 설계 문서, 확보된 리소스, 기술 스택 |
| **출력** | 빌드된 솔루션, 테스트 결과, 배포 가능한 패키지 |
| **관련 프랙티스** | Software Development and Management, Service Validation and Testing |

### 3.5 Transition (전환)

| 항목 | 설명 |
|------|------|
| **목적** | 새로운 제품/서비스를 운영 환경에 안전하게 도입 |
| **핵심 활동** | 배포 계획, 변경 관리, 릴리즈 관리, 사용자 교육 |
| **입력** | 빌드된 솔루션, 변경 요청, 배포 계획 |
| **출력** | 배포된 서비스, 업데이트된 문서, 교육 자료 |
| **관련 프랙티스** | Change Enablement, Release Management, Deployment Management |

### 3.6 Operate (운영)

| 항목 | 설명 |
|------|------|
| **목적** | 서비스의 일상적 운영 유지 |
| **핵심 활동** | 모니터링, 이벤트 관리, 자동화, 가용성 관리 |
| **입력** | 운영 중인 서비스, 모니터링 데이터, 운영 절차 |
| **출력** | 안정적 서비스 운영, 성능 데이터, 이벤트 로그 |
| **관련 프랙티스** | Monitoring and Event Management, Infrastructure and Platform Management |

### 3.7 Deliver (전달)

| 항목 | 설명 |
|------|------|
| **목적** | 고객/사용자에게 가치를 전달 |
| **핵심 활동** | 서비스 카탈로그 관리, 요청 이행, 가치 측정 |
| **입력** | 운영 중인 서비스, 사용자 요청, SLA |
| **출력** | 전달된 서비스 가치, 사용자 만족도 데이터 |
| **관련 프랙티스** | Service Catalogue Management, Service Request Management, Service Level Management |

### 3.8 Support (지원)

| 항목 | 설명 |
|------|------|
| **목적** | 서비스 운영 중 발생하는 이슈와 요청 처리 |
| **핵심 활동** | 인시던트 관리, 문제 관리, 서비스 데스크 운영 |
| **입력** | 인시던트 보고, 사용자 요청, 알려진 오류 |
| **출력** | 해결된 인시던트, 문제 분석 결과, 지식 베이스 업데이트 |
| **관련 프랙티스** | Incident Management, Problem Management, Service Desk |

---

## 4. PSLM의 핵심 특성

### 4.1 반복성 (Iterative)

PSLM은 직선적 모델이 아니다. 팀은 작업의 필요에 따라 활동 간 자유롭게 이동할 수 있다. 예를 들어, Build 중에 새로운 요구사항이 발견되면 Discover로 돌아갈 수 있다.

### 4.2 유연성 (Flexibility)

"One-size-fits-all" 접근을 거부하고, 조직의 상황과 팀의 운영 방식에 맞게 적응할 수 있도록 설계되었다.

### 4.3 가치 공동 창출 중심 (Value Co-creation)

모든 활동이 서비스 제공자와 소비자 간의 가치 공동 창출을 지향한다.

### 4.4 사일로 제거

하나의 통합 라이프사이클 안에서 발견부터 지원까지 전체를 관리하므로, 팀 간 장벽이 줄어든다.

### 4.5 Agile/DevOps 통합

반복적 특성이 Agile 스프린트와 DevOps CI/CD 파이프라인과 자연스럽게 맞닿아 있다.

---

## 5. 실무 적용 시나리오

### 시나리오: 새로운 고객 포털 개발

| 활동 | 적용 예시 |
|------|-----------|
| **Discover** | 고객 설문조사 분석, 경쟁사 포털 벤치마킹, 핵심 기능 우선순위화 |
| **Design** | UI/UX 설계, 마이크로서비스 아키텍처 설계, API 스펙 정의 |
| **Acquire** | AWS 인프라 프로비저닝, 결제 게이트웨이 API 계약, 프론트엔드 개발자 채용 |
| **Build** | React 프론트엔드 개발, Spring Boot 백엔드 개발, 통합 테스트 수행 |
| **Transition** | 스테이징 환경 배포, 베타 테스터 그룹 운영, 사용자 가이드 작성 |
| **Operate** | 프로덕션 모니터링 설정 (Datadog), 자동 스케일링 구성, SRE 온콜 체계 수립 |
| **Deliver** | 서비스 카탈로그에 등록, 고객사별 온보딩, 만족도 조사 실시 |
| **Support** | 서비스 데스크 연동, 인시던트 대응 체계 구축, 지식 베이스 구축 |

---

## 관련 문서

- [ITIL 5 개요](./01-overview.md)
- [ITIL 5 AI 거버넌스와 6C 모델](./03-ai-governance.md)
- [ITIL 5 유지되는 것들 (34개 프랙티스)](./04-practices-continuity.md)
- [ITIL 4 서비스 가치 사슬](../itil4/04-service-value-chain.md)

---

| 이전 | 다음 |
|------|------|
| [<< 01. ITIL 5 개요](./01-overview.md) | [03. AI 거버넌스와 6C 모델 >>](./03-ai-governance.md) |
