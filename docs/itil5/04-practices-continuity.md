# ITIL 5에서 유지되는 것들

## 목차

- [1. 개요](#1-개요)
- [2. 7대 가이딩 원칙 (변경 없음)](#2-7대-가이딩-원칙-변경-없음)
- [3. 4가지 차원 (변경 없음)](#3-4가지-차원-변경-없음)
- [4. 서비스 가치 시스템 (SVS) 기본 구조](#4-서비스-가치-시스템-svs-기본-구조)
- [5. 34개 프랙티스 (용어 현대화)](#5-34개-프랙티스-용어-현대화)
- [6. 핵심 개념과 용어 연속성](#6-핵심-개념과-용어-연속성)

---

## 1. 개요

ITIL 5는 ITIL 4의 **진화(Evolution)**이다. 전면 교체가 아니므로 ITIL 4의 핵심 토대는 그대로 유지된다. 이 문서는 ITIL 5에서 변경되지 않은 핵심 요소들을 정리하여, ITIL 4 학습자가 기존 지식을 그대로 활용할 수 있음을 확인하는 데 목적이 있다.

### 유지 vs 변경 요약

| 구분 | 상태 | 설명 |
|------|------|------|
| 7대 가이딩 원칙 | **완전 유지** | 명칭과 내용 동일 |
| 4가지 차원 | **완전 유지** | 명칭과 내용 동일 |
| 서비스 가치 시스템 (SVS) | **기본 구조 유지** | 명칭이 ITIL Value System으로 변경 |
| 34개 프랙티스 | **모두 유지** | 용어만 일부 현대화 |
| 서비스 가치 사슬 | **확장 변경** | PSLM 8개 활동으로 확장 |
| 거버넌스 | **방식 변경** | 작업에 가까이 위치하도록 재배치 |

---

## 2. 7대 가이딩 원칙 (변경 없음)

ITIL 4의 7대 가이딩 원칙은 ITIL 5에서도 **완전히 동일하게 유지**된다.

| # | 원칙 (한국어) | 영문 | 설명 |
|---|-------------|------|------|
| 1 | 가치에 집중하라 | Focus on Value | 모든 활동은 이해관계자를 위한 가치 창출에 직간접적으로 연결되어야 한다 |
| 2 | 현재 위치에서 시작하라 | Start Where You Are | 기존 자산과 역량을 먼저 평가하고 활용하라 |
| 3 | 피드백과 함께 반복적으로 진행하라 | Progress Iteratively with Feedback | 작은 단위로 반복하며 피드백을 통해 개선하라 |
| 4 | 협력하고 가시성을 높여라 | Collaborate and Promote Visibility | 이해관계자와 협력하고 투명성을 유지하라 |
| 5 | 전체적으로 사고하고 일하라 | Think and Work Holistically | 부분이 아닌 전체 시스템 관점에서 사고하라 |
| 6 | 단순하고 실용적으로 유지하라 | Keep It Simple and Practical | 불필요한 복잡성을 제거하고 실용적 접근을 취하라 |
| 7 | 최적화하고 자동화하라 | Optimize and Automate | 먼저 최적화한 후 자동화를 적용하라 |

### ITIL 5에서의 적용 확대

원칙 자체는 변경되지 않았지만, ITIL 5에서는 이 원칙들이 적용되는 **범위가 확대**되었다.

| 원칙 | ITIL 4 적용 범위 | ITIL 5 확대 적용 |
|------|-----------------|-----------------|
| 가치에 집중 | 서비스 가치 | 제품 + 서비스 가치 + 사용자 경험 |
| 최적화하고 자동화 | IT 프로세스 자동화 | AI 기반 자동화, 지능형 자동화 포함 |
| 전체적으로 사고 | 서비스 관리 전체 | 제품 라이프사이클 전체 + AI 거버넌스 포함 |

---

## 3. 4가지 차원 (변경 없음)

ITIL 4의 서비스 관리 4가지 차원은 ITIL 5에서도 **동일하게 유지**된다.

| # | 차원 (한국어) | 영문 | 핵심 질문 |
|---|-------------|------|-----------|
| 1 | 조직과 사람 | Organizations and People | "누가 서비스를 관리하고 전달하는가?" |
| 2 | 정보와 기술 | Information and Technology | "어떤 정보와 기술이 서비스를 지원하는가?" |
| 3 | 파트너와 공급업체 | Partners and Suppliers | "어떤 외부 파트너가 가치 창출에 기여하는가?" |
| 4 | 가치 흐름과 프로세스 | Value Streams and Processes | "어떻게 가치가 만들어지고 전달되는가?" |

### ITIL 5에서의 변화 포인트

차원 자체는 동일하지만, **정보와 기술(Information and Technology)** 차원에서 AI 관련 내용이 크게 보강되었다. 특히 6C 모델이 이 차원 안에서 AI 역량을 분류하는 데 활용된다.

---

## 4. 서비스 가치 시스템 (SVS) 기본 구조

ITIL 4의 SVS 기본 구조는 유지되지만, 명칭이 **ITIL Value System**으로 변경되었다.

### SVS 구성 요소 비교

| 구성 요소 | ITIL 4 | ITIL 5 |
|----------|--------|--------|
| 가이딩 원칙 | 7개 원칙 (동일) | 7개 원칙 (동일) |
| 거버넌스 | 작업 위에서 검토/승인 | 작업에 가까이 위치 |
| 서비스 가치 사슬 | 6개 활동 (SVC) | 8개 활동 (PSLM = ITIL Value Chain) |
| 프랙티스 | 34개 | 34개 (용어 현대화) |
| 지속적 개선 | 명시적 활동 | 전체 라이프사이클에 내재화 |

---

## 5. 34개 프랙티스 (용어 현대화)

ITIL 4의 34개 프랙티스는 ITIL 5에서 **모두 유지**된다. 일부 프랙티스의 용어만 현대적 관행을 반영하여 업데이트되었다.

### 일반 관리 프랙티스 (General Management Practices) - 14개

| # | 프랙티스 | 영문 | ITIL 5 변경사항 |
|---|---------|------|---------------|
| 1 | 아키텍처 관리 | Architecture Management | 용어 현대화 |
| 2 | 지속적 개선 | Continual Improvement | 유지 |
| 3 | 정보 보안 관리 | Information Security Management | AI 보안 관점 추가 |
| 4 | 지식 관리 | Knowledge Management | 유지 |
| 5 | 측정 및 보고 | Measurement and Reporting | 경험 지표 포함 |
| 6 | 조직 변화 관리 | Organizational Change Management | 유지 |
| 7 | 포트폴리오 관리 | Portfolio Management | 제품 포트폴리오 확장 |
| 8 | 프로젝트 관리 | Project Management | 유지 |
| 9 | 관계 관리 | Relationship Management | 서비스 관계 모델 연계 |
| 10 | 리스크 관리 | Risk Management | AI 리스크 포함 |
| 11 | 서비스 재무 관리 | Service Financial Management | 유지 |
| 12 | 전략 관리 | Strategy Management | 디지털 전략 강화 |
| 13 | 공급업체 관리 | Supplier Management | 유지 |
| 14 | 인력 및 인재 관리 | Workforce and Talent Management | 유지 |

### 서비스 관리 프랙티스 (Service Management Practices) - 17개

| # | 프랙티스 | 영문 | ITIL 5 변경사항 |
|---|---------|------|---------------|
| 1 | 가용성 관리 | Availability Management | 유지 |
| 2 | 비즈니스 분석 | Business Analysis | 유지 |
| 3 | 용량 및 성능 관리 | Capacity and Performance Management | 유지 |
| 4 | 변경 지원 | Change Enablement | 유지 |
| 5 | 인시던트 관리 | Incident Management | 유지 |
| 6 | IT 자산 관리 | IT Asset Management | 유지 |
| 7 | 모니터링 및 이벤트 관리 | Monitoring and Event Management | AI 모니터링 확장 |
| 8 | 문제 관리 | Problem Management | 유지 |
| 9 | 릴리즈 관리 | Release Management | 유지 |
| 10 | 서비스 카탈로그 관리 | Service Catalogue Management | 유지 |
| 11 | 서비스 구성 관리 | Service Configuration Management | 유지 |
| 12 | 서비스 연속성 관리 | Service Continuity Management | 유지 |
| 13 | 서비스 설계 | Service Design | 경험 설계 강화 |
| 14 | 서비스 데스크 | Service Desk | AI 챗봇 통합 |
| 15 | 서비스 수준 관리 | Service Level Management | 경험 수준 포함 |
| 16 | 서비스 요청 관리 | Service Request Management | 유지 |
| 17 | 서비스 검증 및 테스트 | Service Validation and Testing | 유지 |

### 기술 관리 프랙티스 (Technical Management Practices) - 3개

| # | 프랙티스 | 영문 | ITIL 5 변경사항 |
|---|---------|------|---------------|
| 1 | 배포 관리 | Deployment Management | 유지 |
| 2 | 인프라 및 플랫폼 관리 | Infrastructure and Platform Management | 클라우드 네이티브 강화 |
| 3 | 소프트웨어 개발 및 관리 | Software Development and Management | 유지 |

---

## 6. 핵심 개념과 용어 연속성

ITIL 4에서 학습한 다음 핵심 개념들은 ITIL 5에서도 그대로 적용된다.

| 개념 | 상태 | 비고 |
|------|------|------|
| 가치 (Value) | 유지 | 가치 공동 창출 원칙 동일 |
| 서비스 (Service) | 유지 | 제품(Product) 개념 추가됨 |
| 유틸리티 (Utility) | 유지 | Fit for Purpose |
| 보증 (Warranty) | 유지 | Fit for Use |
| 결과 (Outcome) | 유지 | - |
| 산출물 (Output) | 유지 | - |
| 리스크 (Risk) | 유지 | AI 리스크 범위 확대 |
| 서비스 관계 (Service Relationship) | 확장 | 서비스 관계 모델로 체계화 |
| 가치 공동 창출 (Value Co-creation) | 유지 | 핵심 원칙 동일 |

---

## 관련 문서

- [ITIL 5 개요](./01-overview.md)
- [ITIL 5 AI 거버넌스와 6C 모델](./03-ai-governance.md)
- [ITIL 4 7대 지도 원칙 (상세)](../itil4/02-guiding-principles.md)
- [ITIL 4 34개 프랙티스 - 일반 관리](../itil4/06-practices-general.md)

---

| 이전 | 다음 |
|------|------|
| [<< 03. AI 거버넌스와 6C 모델](./03-ai-governance.md) | [05. 거버넌스와 경험 관리 >>](./05-governance-experience.md) |
