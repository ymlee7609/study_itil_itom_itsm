# Service vs Product vs Service Offering

ITIL 4에서 새로 정리되고 ITIL 5 **PSLM**(Product & Service Lifecycle Management)에서 핵심축이 되는 3개 개념. 소프트웨어 업계와 ITIL의 정의가 미묘히 다르다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 포함 관계](#2-포함-관계)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의 (ITIL 4/5 기준)

| 구분 | Product (제품) | Service (서비스) | Service Offering (서비스 제공 패키지) |
|------|---------------|-----------------|--------------------------------------|
| **정의** | 고객에게 **가치를 제공하기 위해 구성된 자원 집합** | 고객이 원하는 **outcome 달성을 촉진**하는 수단 | 특정 소비자 그룹을 위한 **서비스의 공식 서술** (메뉴) |
| **관점** | 제공자 내부 시각 | 제공자-소비자 관계 시각 | 시장·소비자 선택 시각 |
| **예** | 메일 플랫폼 시스템(인프라+코드+운영 매뉴얼) | "기업 메일 서비스" | "스타터 10GB / 프로 50GB / 엔터프라이즈 무제한" |
| **수량 관계** | 1개 Product | 1개 이상 Service | Service당 여러 Offering |

**핵심 구분 (ITIL 4 공식)**:
- **Product** = 자원·구성요소의 **집합** (명사적, 실체)
- **Service** = 가치 **교환 관계** (동사적, 작용)
- **Service Offering** = 시장에 내놓는 **상품 포장** (메뉴화)

---

## 2. 포함 관계

```
        Product (제품)
    ┌───────────────────────┐
    │  자원 집합             │
    │  - 인프라              │
    │  - 애플리케이션 코드    │
    │  - 프로세스            │
    │  - 지식                │
    └───────────┬───────────┘
                │ 구성되어 제공됨
                ▼
        Service (서비스)
    ┌───────────────────────┐
    │  제공자 ↔ 소비자 관계    │
    │  outcome 촉진          │
    └───────────┬───────────┘
                │ 패키징되어 제시됨
                ▼
    Service Offering (제공 패키지)
    ┌───────────┬───────────┐
    │  Starter  │   Pro     │   Enterprise
    │  $ 10/월  │  $ 50/월  │   계약 별도
    └───────────┴───────────┘
```

**관계식**:
- 1 Product → **N** Services
- 1 Service → **N** Offerings

---

## 3. 실무 예시

### 예시 1: Microsoft 365

| 층위 | 예시 |
|------|------|
| **Product** | M365 플랫폼 (Azure AD + Exchange + SharePoint + Teams 통합 인프라) |
| **Service** | "기업용 협업 서비스" |
| **Service Offerings** | Business Basic / Business Standard / Business Premium / E3 / E5 |

### 예시 2: 사내 ERP

| 층위 | 예시 |
|------|------|
| Product | SAP S/4HANA 인스턴스 + 커스터마이징 + 연동 데이터 파이프라인 |
| Service | "재무·회계·구매 통합 서비스" |
| Offerings | "재무팀용 풀 권한 / 영업팀용 구매 권한 / 조회 전용" |

### 예시 3: 이동통신 (업계 실무)

| 층위 | 예시 |
|------|------|
| Product | 5G 네트워크 인프라 + 코어망 + 과금 시스템 |
| Service | "모바일 통신 서비스" |
| Offerings | "5G 무제한 / 5G 100GB / LTE 데이터중심 등 요금제" |

### 예시 4: 구성요소 세분화

| 항목 | 분류 |
|------|------|
| 서버 하드웨어 | Product의 **구성요소** (CI) |
| 데이터베이스 스키마 | Product의 **구성요소** |
| "계정 생성" 기능 | Service의 **구성요소** |
| "프리미엄 지원 포함" | Service Offering의 **차별화 요소** |

---

## 4. 왜 이 구분이 중요한가

### (1) ITIL 5 PSLM의 축

ITIL 5는 **Product & Service Lifecycle Management(PSLM)**를 핵심 모델로 도입:
- ITIL 4의 서비스 중심 → **Product+Service 동시 관리**
- 이유: 디지털 제품화(Productization) 트렌드 반영
- Product 기반 조직·팀 구조 강조 (Spotify 모델 등)

### (2) 책임 소재 명확화

| 층위 | 책임자 | 관심사 |
|------|--------|--------|
| Product | Product Manager / Platform Engineer | 기술·플랫폼·아키텍처 |
| Service | Service Owner / Service Manager | SLA·운영·관계 |
| Offering | Offering Manager / Product Marketing | 가격·패키징·시장 |

→ 대기업일수록 3역이 분리. 뭉치면 책임 전가 발생.

### (3) 내부 카탈로그 vs 외부 카탈로그

| 대상 | 내용 |
|------|------|
| **Technical Service Catalog** | Product·기술적 구성 (내부용) |
| **Business Service Catalog** | Service·Service Offering (고객용) |

서비스 데스크·고객은 Business Catalog만 보고 선택. Technical Catalog는 내부 운영용.

### (4) 가격 설계와 Offering

- Service 자체에 가격은 없음
- **Service Offering 단위**로 가격 책정
- 같은 Service라도 Offering에 따라 SLA·기능·가격 차등 가능

### (5) 제품 철수/EoL 관리

- Offering 철수 ≠ Service 철수 ≠ Product 철수
- "Starter 플랜 단종"(Offering EoL)과 "해당 Service 전체 종료"는 완전히 다른 이벤트

### (6) Cloud·SaaS 시대의 적합성

- 전통 IT: Product 개념 희박, Service 중심
- 클라우드: AWS·Azure 등이 **Product 중심으로 조직** (EC2, S3, Lambda 등 각각이 Product)
- 내부 IT도 이제 Platform as a Product 트렌드 → 조직 재편 필요

---

## 5. 한눈 정리

```
Product           Service              Service Offering
(제품)            (서비스)              (제공 패키지)
─────            ───────              ──────────────
자원 집합         관계·작용             메뉴·상품
기술·플랫폼       outcome 촉진          가격·패키징
Product Manager   Service Owner         Offering Manager
Technical Catalog Business Catalog      Sales Catalog
```

---

## 한 줄 요약

**Product는 자원 집합(내부 구성), Service는 고객 outcome 촉진(관계), Service Offering은 시장에 내놓는 패키지(메뉴).** 1 Product → N Services → N Offerings의 계층 관계. ITIL 5의 PSLM이 이 셋을 생애주기로 통합 관리한다.

---

## 관련 문서

- [ITIL 4 개요](../itil4/01-overview.md)
- [ITIL 5 제품 및 서비스 라이프사이클](../itil5/02-product-service-lifecycle.md)
- [ITIL 4 vs ITIL 5 종합 비교](../itil4-vs-itil5/01-comprehensive-comparison.md)
- [Output vs Outcome](output_vs_outcome.md)
