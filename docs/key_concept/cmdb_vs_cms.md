# CMDB vs CMS vs Asset Registry

구성 관리의 3개 저장소. "CMDB"라는 용어로 다 뭉뚱그려 쓰지만, **데이터 범위·관리 목적·통합 수준**이 다르다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 포함 관계](#2-포함-관계)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | CMDB | CMS | Asset Registry |
|------|------|-----|----------------|
| **풀네임** | Configuration Management **Database** | Configuration Management **System** | IT Asset Register |
| **범위** | CI 정보 단일 DB | CMDB + KEDB + 정의 라이브러리 + 지식 등 **구성관리 전체 시스템** | IT 자산의 재무·계약·생애주기 원장 |
| **목적** | 서비스 관계·의존성 추적 | 서비스 구성 관련 **모든 정보 통합** | 재무·감사·라이선스 관리 |
| **내용** | CI 속성, 관계, 상태 | CMDB + Change 기록 + Release 정보 + 표준 베이스라인 | 구매가, 감가상각, 계약, 소유자 |
| **담당** | Service Configuration Management | 동일 | IT Asset Management |

---

## 2. 포함 관계

```
           CMS (Configuration Management System)
  ┌─────────────────────────────────────────────────┐
  │                                                 │
  │   ┌─────────┐   ┌──────────┐   ┌──────────┐     │
  │   │  CMDB   │   │   KEDB   │   │ Definitive│    │
  │   │         │   │ (Known   │   │ Media     │    │
  │   │  CI들   │   │ Errors)  │   │ Library)  │    │
  │   └─────────┘   └──────────┘   └──────────┘     │
  │                                                 │
  │   ┌─────────┐   ┌──────────┐                    │
  │   │ Change  │   │  Service │                    │
  │   │ Records │   │ Catalog  │                    │
  │   └─────────┘   └──────────┘                    │
  │                                                 │
  └─────────────────────────────────────────────────┘

  ─────────────────────────────────────────────────
  
       Asset Registry (별도 시스템 가능)
  ┌─────────────────────────────────────────────────┐
  │                                                 │
  │  재무 원장 + 계약서 + 라이선스 + 감가상각        │
  │                                                 │
  └─────────────────────────────────────────────────┘
           ▲                                │
           │   (같은 실물 = 양쪽에 존재)     │
           │                                ▼
       교차 참조로 연결 (CI-Asset Mapping)
```

**포함 관계**:
- CMS ⊃ CMDB (CMS는 CMDB를 **포함**하는 더 큰 개념)
- CMDB vs Asset Registry는 **교집합 있는 별도 시스템** (→ [CI vs Asset 참고](ci_vs_asset.md))

---

## 3. 실무 예시

### 예시 1: ServiceNow에서의 구현

| 구분 | ServiceNow 모듈 |
|------|----------------|
| CMDB | Configuration Management > CI 테이블군 |
| CMS | ITSM 전체 플랫폼 (CMDB + Change + Problem + KEDB + Catalog 통합) |
| Asset Registry | IT Asset Management (별도 모듈, Asset 테이블) |
| 연결 | CI ↔ Asset 필드 매핑 (1:1 또는 1:N) |

### 예시 2: 물리 서버 한 대의 기록 위치

| 정보 | 저장소 |
|------|--------|
| 호스트명, IP, 역할 | **CMDB** (CI 레코드) |
| 의존 서비스 관계 | **CMDB** |
| 최근 Change 기록 | **CMS** (Change 테이블, CI에 연결) |
| 알려진 이슈 목록 | **CMS** (KEDB, CI에 연결) |
| 구매가, 구매일 | **Asset Registry** |
| 보증·유지보수 계약서 | **Asset Registry** |
| 감가상각 현황 | **Asset Registry** (또는 재무 시스템) |

### 예시 3: 기업별 성숙도 단계

| 성숙도 | 상태 |
|--------|------|
| **낮음** | 엑셀 파일 1장에 CI·Asset·이슈 혼재. CMDB라 부름 |
| **중간** | CMDB 도구 도입, Asset Registry는 별도 재무 시스템에 |
| **높음** | CMS로 통합 (CMDB + KEDB + Change 연결), Asset Registry와 ID 매핑 |
| **최상** | Discovery 자동화로 CMS 실시간 갱신, Asset은 계약 시스템과 연동 |

---

## 4. 왜 이 구분이 중요한가

### (1) "CMDB 프로젝트"의 흔한 실패

- "CMDB 구축"을 목표로 했는데 실제로는 **CMS 수준**을 원함
- 결과: CMDB만 도입 → KEDB·Change 연결 누락 → "DB는 있는데 안 씀"
- 대안: 처음부터 **CMS 관점**에서 범위 정의

### (2) "CMDB에 모든 자산을" 함정

- CMDB에 Asset 재무 정보를 우겨넣음 → 데이터 오염
- Asset Registry의 재무·계약 정보는 **갱신 주기·소유 부서**가 다름
- → CMDB와 Asset Registry는 **연결하되 분리**

### (3) Discovery의 범위

- Discovery 도구 (ServiceNow Discovery, Device42, Lansweeper): CMDB 자동 갱신
- 그러나 **Asset Registry의 구매가·계약**은 자동 탐지 불가
- → Discovery로 CMDB만, Asset은 **구매·계약 시스템과 연동** 필요

### (4) 감사 대응

| 감사 유형 | 참조 대상 |
|----------|----------|
| IT 서비스 감사 | **CMS** (CI·Change·이슈 추적 가능 여부) |
| 재무 감사 | **Asset Registry** (감가상각, 실재 확인) |
| 라이선스 감사 (MS, Oracle) | Asset Registry + CMDB (설치 vs 계약) |
| 보안 감사 (ISMS) | CMS (보안 CI 관리) + Asset Registry (계약) |

### (5) 데이터 정합성 관리

- CMDB ↔ Asset Registry 간 **ID 매핑 필수**
- 불일치 시 "CMDB엔 있는데 Asset엔 없는 서버" (소위 Ghost Asset) 발생
- 정기 **reconciliation** 프로세스 필요

### (6) 클라우드·SaaS 시대의 재정의

| 자원 | CMDB | Asset Registry |
|------|------|---------------|
| EC2 인스턴스 | ○ (동적 CI) | △ (계정 단위 Asset) |
| Lambda 함수 | ○ (CI) | ✗ (사용량 기반) |
| SaaS 구독 (Salesforce) | △ (논리 CI) | ○ (계약 Asset) |
| 개인 노트북 | ○ (CI) | ○ (Asset) |

---

## 5. 한눈 정리

```
        CMS (Configuration Management System)
  ┌──────────────────────────────────────────────┐
  │                                              │
  │  CMDB ─ 서비스 관점의 CI 저장소                │
  │   │                                          │
  │   ├── CI 속성·관계·상태                       │
  │   ├── 서비스 매핑                             │
  │   └── 의존성 그래프                           │
  │                                              │
  │  + KEDB + Change Records + Service Catalog   │
  │                                              │
  └──────────────────────────────────────────────┘
  
  Asset Registry (별도 시스템)
  ┌──────────────────────────────────────────────┐
  │  재무·계약·라이선스·감가상각 원장             │
  │  (CI와 1:1 매핑 유지)                         │
  └──────────────────────────────────────────────┘
```

---

## 한 줄 요약

**CMDB는 CI 저장소(서비스 관계 추적), CMS는 CMDB+KEDB+Change 등 구성관리 전체 시스템, Asset Registry는 재무·계약·생애주기 원장.** CMS ⊃ CMDB이며, Asset Registry는 별도 시스템으로 CMDB와 ID 매핑만 유지한다.

---

## 관련 문서

- [CI vs Asset](ci_vs_asset.md)
- [ITAM vs ITSM vs ITOM 비교](../itam/02-itam-vs-itsm-itom.md)
- [ITAM 개요](../itam/01-overview.md)
- [ITIL 4 서비스 관리 프랙티스](../itil4/07-practices-service.md)
