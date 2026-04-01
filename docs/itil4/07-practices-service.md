# 서비스 관리 프랙티스 (Service Management Practices)

## 목차

- [1. 개요](#1-개요)
- [2. 가용성 관리 (Availability Management)](#2-가용성-관리-availability-management)
- [3. 비즈니스 분석 (Business Analysis)](#3-비즈니스-분석-business-analysis)
- [4. 용량 및 성능 관리 (Capacity and Performance Management)](#4-용량-및-성능-관리-capacity-and-performance-management)
- [5. 변경 지원 (Change Enablement)](#5-변경-지원-change-enablement)
- [6. 인시던트 관리 (Incident Management)](#6-인시던트-관리-incident-management)
- [7. IT 자산 관리 (IT Asset Management)](#7-it-자산-관리-it-asset-management)
- [8. 모니터링 및 이벤트 관리 (Monitoring and Event Management)](#8-모니터링-및-이벤트-관리-monitoring-and-event-management)
- [9. 문제 관리 (Problem Management)](#9-문제-관리-problem-management)
- [10. 릴리스 관리 (Release Management)](#10-릴리스-관리-release-management)
- [11. 서비스 카탈로그 관리 (Service Catalogue Management)](#11-서비스-카탈로그-관리-service-catalogue-management)
- [12. 서비스 구성 관리 (Service Configuration Management)](#12-서비스-구성-관리-service-configuration-management)
- [13. 서비스 연속성 관리 (Service Continuity Management)](#13-서비스-연속성-관리-service-continuity-management)
- [14. 서비스 설계 (Service Design)](#14-서비스-설계-service-design)
- [15. 서비스 데스크 (Service Desk)](#15-서비스-데스크-service-desk)
- [16. 서비스 수준 관리 (Service Level Management)](#16-서비스-수준-관리-service-level-management)
- [17. 서비스 요청 관리 (Service Request Management)](#17-서비스-요청-관리-service-request-management)
- [18. 서비스 검증 및 테스트 (Service Validation and Testing)](#18-서비스-검증-및-테스트-service-validation-and-testing)
- [19. 전체 요약표](#19-전체-요약표)

---

## 1. 개요

**서비스 관리 프랙티스 (Service Management Practices)**는 IT 서비스 관리 분야에서 발전해온 프랙티스이다. 총 **17개**의 프랙티스로 구성된다.

| 항목 | 설명 |
|------|------|
| 적용 범위 | IT 서비스 관리 (ITSM) |
| 개수 | 17개 |
| 기원 | IT 서비스 관리 업계에서 발전 |
| 특징 | ITIL 4에서 가장 핵심적인 프랙티스 그룹 |

---

## 2. 가용성 관리 (Availability Management)

| 항목 | 설명 |
|------|------|
| 목적 | 서비스가 합의된 수준의 가용성을 제공하도록 보장 |
| 핵심 활동 | 가용성 요구사항 분석, 가용성 설계, 가용성 모니터링/보고 |
| 핵심 지표 | 가용률(%), MTBF(평균 장애 간격), MTRS(평균 복구 시간) |
| 관련 개념 | 고가용성(HA), 장애 허용(Fault Tolerance), 복원력(Resilience) |

---

## 3. 비즈니스 분석 (Business Analysis)

| 항목 | 설명 |
|------|------|
| 목적 | 비즈니스 요구를 분석하고 해결책을 권고하여 이해관계자에게 가치 제공 |
| 핵심 활동 | 요구사항 수집, 분석, 문서화, 해결책 평가 |
| 산출물 | 비즈니스 케이스, 요구사항 명세서, 프로세스 모델 |
| ITIL 4 신규 | v3에는 없었으나 ITIL 4에서 새로 추가 |

---

## 4. 용량 및 성능 관리 (Capacity and Performance Management)

| 항목 | 설명 |
|------|------|
| 목적 | 서비스가 합의된 수준의 용량과 성능을 달성하도록 보장 |
| 핵심 활동 | 용량 계획, 성능 모니터링, 수요 예측, 용량 조정 |
| 핵심 지표 | 응답 시간, 처리량(Throughput), CPU/메모리 사용률 |
| 클라우드 연관 | Auto-scaling, 탄력적 용량 관리 |

---

## 5. 변경 지원 (Change Enablement)

| 항목 | 설명 |
|------|------|
| 목적 | 리스크를 적절히 관리하면서 성공적인 변경을 극대화 |
| 핵심 활동 | 변경 요청 평가, 승인, 일정 관리, 검토 |
| v3와 차이 | Change Management → Change Enablement로 명칭 변경 |
| 핵심 산출물 | 변경 일정 (Change Schedule), 변경 기록 |

### 변경 유형

| 유형 | 영문 | 설명 | 승인 |
|------|------|------|------|
| 표준 변경 | Standard Change | 사전 승인된 저위험 변경 | 사전 승인 (Pre-authorized) |
| 일반 변경 | Normal Change | 일정에 따라 평가/승인되는 변경 | 변경 권한자 (Change Authority) |
| 긴급 변경 | Emergency Change | 신속히 실행해야 하는 변경 | 긴급 CAB (ECAB) |

> 상세 내용: [09. 핵심 프로세스 심화](./09-key-processes.md)

---

## 6. 인시던트 관리 (Incident Management)

| 항목 | 설명 |
|------|------|
| 목적 | 서비스의 비계획적 중단이나 서비스 품질 저하의 부정적 영향을 최소화 |
| 핵심 활동 | 인시던트 감지, 기록, 분류, 우선순위 결정, 진단, 해결, 종료 |
| 핵심 지표 | MTTR(평균 해결 시간), 인시던트 수, 재발률 |
| 핵심 개념 | 우선순위(Priority), 에스컬레이션(Escalation), Major Incident |

> 상세 내용: [09. 핵심 프로세스 심화](./09-key-processes.md)

---

## 7. IT 자산 관리 (IT Asset Management)

| 항목 | 설명 |
|------|------|
| 목적 | 조직의 IT 자산을 전체 수명주기에 걸쳐 계획하고 관리 |
| 핵심 활동 | 자산 등록, 추적, 최적화, 폐기 |
| 자산 유형 | 하드웨어, 소프트웨어 라이선스, 클라우드 구독 |
| 관련 분야 | 소프트웨어 자산 관리 (SAM), 하드웨어 자산 관리 (HAM) |

---

## 8. 모니터링 및 이벤트 관리 (Monitoring and Event Management)

| 항목 | 설명 |
|------|------|
| 목적 | 이벤트를 체계적으로 관찰하고 적절한 관리 조치를 결정/실행 |
| 핵심 활동 | 모니터링 설정, 이벤트 감지, 이벤트 필터링/분류, 대응 |

### 이벤트 유형

| 유형 | 영문 | 설명 | 조치 |
|------|------|------|------|
| 정보성 | Informational | 정상 운영 확인 | 기록만 |
| 경고 | Warning | 임계치 접근, 주의 필요 | 모니터링 강화 |
| 예외 | Exception | 비정상 상황, 즉각 대응 필요 | 인시던트 생성 |

---

## 9. 문제 관리 (Problem Management)

| 항목 | 설명 |
|------|------|
| 목적 | 인시던트의 근본 원인을 파악하여 인시던트 발생 가능성과 영향을 줄임 |
| 핵심 활동 | 문제 식별, 근본 원인 분석(RCA), 해결책 도출, 알려진 오류(Known Error) 관리 |
| 접근 방식 | 사후적 (Reactive) + 사전적 (Proactive) |
| 핵심 개념 | 근본 원인 (Root Cause), 알려진 오류 (Known Error), 임시 해결책 (Workaround) |

> 상세 내용: [09. 핵심 프로세스 심화](./09-key-processes.md)

---

## 10. 릴리스 관리 (Release Management)

| 항목 | 설명 |
|------|------|
| 목적 | 신규/변경된 서비스와 기능을 사용 가능하도록 만듦 |
| 핵심 활동 | 릴리스 계획, 구축, 테스트, 배포 승인 |
| 배포 관리와 차이 | 릴리스 = "무엇을" 배포할지 결정, 배포 = "어떻게" 설치할지 실행 |
| 릴리스 유형 | Major, Minor, Patch, Emergency |

---

## 11. 서비스 카탈로그 관리 (Service Catalogue Management)

| 항목 | 설명 |
|------|------|
| 목적 | 사용 가능한 서비스에 대한 정확하고 일관된 정보를 제공 |
| 핵심 활동 | 카탈로그 생성, 유지, 공개, 접근성 보장 |
| 대상 | 비즈니스 서비스 카탈로그, 기술 서비스 카탈로그 |
| 포함 정보 | 서비스 설명, SLA, 비용, 요청 방법, 지원 시간 |

---

## 12. 서비스 구성 관리 (Service Configuration Management)

| 항목 | 설명 |
|------|------|
| 목적 | 서비스와 구성 항목(CI)에 대한 정확하고 신뢰할 수 있는 정보를 유지 |
| 핵심 활동 | CI 식별, 기록, 관계 매핑, 상태 추적, 검증/감사 |
| 핵심 개념 | CI (Configuration Item), CMDB (Configuration Management Database), CMS (Configuration Management System) |
| 관리 대상 | 서버, 애플리케이션, 문서, SLA, 네트워크 장비 등 |

---

## 13. 서비스 연속성 관리 (Service Continuity Management)

| 항목 | 설명 |
|------|------|
| 목적 | 재난 상황에서도 합의된 수준의 서비스 가용성과 성능을 보장 |
| 핵심 활동 | BIA(비즈니스 영향 분석), 리스크 평가, 복구 계획, 테스트/훈련 |
| 핵심 지표 | RTO(복구 시간 목표), RPO(복구 시점 목표) |
| 관련 | BCP(비즈니스 연속성 계획), DR(재해 복구) |

---

## 14. 서비스 설계 (Service Design)

| 항목 | 설명 |
|------|------|
| 목적 | 제품과 서비스를 목적에 맞고 사용에 적합하도록 설계 |
| 핵심 활동 | 서비스 요구사항 분석, 아키텍처 설계, 프로세스 설계 |
| 설계 요소 | 유틸리티(Utility)와 보증(Warranty) 모두 충족 |
| 접근 방식 | 사용자 중심 설계 (User-centered Design) |

---

## 15. 서비스 데스크 (Service Desk)

| 항목 | 설명 |
|------|------|
| 목적 | IT와 사용자 간의 단일 접점(SPOC)으로서 인시던트와 서비스 요청 처리 |
| 핵심 활동 | 요청 접수, 분류, 1차 해결, 에스컬레이션, 커뮤니케이션 |
| 유형 | 로컬(Local), 중앙(Centralized), 가상(Virtual), 팔로더선(Follow-the-Sun) |
| ITIL 4 변화 | v3의 "기능(Function)"에서 ITIL 4의 "프랙티스(Practice)"로 변경 |

### 서비스 데스크 유형 비교

| 유형 | 특징 | 적합한 조직 |
|------|------|-----------|
| 로컬 (Local) | 사용자와 같은 물리적 위치 | 소규모, 단일 사업장 |
| 중앙 (Centralized) | 하나의 중앙 조직에서 모든 사용자 지원 | 중대규모, 비용 효율 중시 |
| 가상 (Virtual) | 분산된 팀이 기술 기반으로 통합 운영 | 글로벌, 분산 조직 |
| 팔로더선 (Follow-the-Sun) | 시간대별 교대로 24시간 지원 | 글로벌, 24/7 서비스 필요 |

---

## 16. 서비스 수준 관리 (Service Level Management)

| 항목 | 설명 |
|------|------|
| 목적 | 서비스 수준에 대한 명확한 비즈니스 기반 목표를 설정하고 달성 보장 |
| 핵심 활동 | SLA 정의/협의, 서비스 수준 모니터링, 서비스 검토 |
| 핵심 산출물 | SLA (Service Level Agreement), OLA (Operational Level Agreement) |
| ITIL 4 강조 | 기술 지표(가동률)보다 비즈니스 성과 중심의 SLA 권장 |

### SLA vs OLA vs UC

| 합의/계약 | 영문 | 당사자 | 용도 |
|----------|------|--------|------|
| SLA | Service Level Agreement | 서비스 제공자 ↔ 고객 | 서비스 수준 합의 |
| OLA | Operational Level Agreement | 내부 지원 조직 간 | 내부 지원 수준 합의 |
| UC | Underpinning Contract | 서비스 제공자 ↔ 외부 공급자 | 외부 공급 계약 |

---

## 17. 서비스 요청 관리 (Service Request Management)

| 항목 | 설명 |
|------|------|
| 목적 | 사전 정의된 서비스 요청을 효율적이고 사용자 친화적으로 처리 |
| 핵심 활동 | 요청 접수, 이행, 종료, 만족도 확인 |
| 요청 유형 | 정보 요청, 접근 권한 요청, 자원 요청, 피드백/불만 |
| 자동화 | 셀프서비스 포털, 워크플로우 자동화 권장 |

> 상세 내용: [09. 핵심 프로세스 심화](./09-key-processes.md)

---

## 18. 서비스 검증 및 테스트 (Service Validation and Testing)

| 항목 | 설명 |
|------|------|
| 목적 | 신규/변경된 서비스가 정의된 요구사항을 충족하는지 확인 |
| 핵심 활동 | 테스트 계획, 테스트 실행, 결과 보고, 결함 관리 |
| 테스트 유형 | 기능 테스트, 비기능 테스트, 회귀 테스트, UAT |
| 자동화 | 자동화 테스트(CI/CD 파이프라인 내) 권장 |

---

## 19. 전체 요약표

| 번호 | 프랙티스 (한국어) | 영문 | 핵심 목적 |
|------|----------------|------|----------|
| 1 | 가용성 관리 | Availability Management | 합의된 서비스 가용성 보장 |
| 2 | 비즈니스 분석 | Business Analysis | 비즈니스 요구 분석 및 해결책 권고 |
| 3 | 용량 및 성능 관리 | Capacity and Performance Management | 서비스 용량/성능 목표 달성 |
| 4 | 변경 지원 | Change Enablement | 리스크 관리하며 변경 성공 극대화 |
| 5 | 인시던트 관리 | Incident Management | 서비스 중단의 영향 최소화 |
| 6 | IT 자산 관리 | IT Asset Management | IT 자산 수명주기 관리 |
| 7 | 모니터링 및 이벤트 관리 | Monitoring and Event Management | 이벤트 감지 및 적절한 대응 |
| 8 | 문제 관리 | Problem Management | 인시던트 근본 원인 파악 및 예방 |
| 9 | 릴리스 관리 | Release Management | 서비스/기능의 사용 가능성 확보 |
| 10 | 서비스 카탈로그 관리 | Service Catalogue Management | 서비스 정보 정확성 유지 |
| 11 | 서비스 구성 관리 | Service Configuration Management | CI 정보 정확성 및 신뢰성 유지 |
| 12 | 서비스 연속성 관리 | Service Continuity Management | 재난 시 서비스 연속성 보장 |
| 13 | 서비스 설계 | Service Design | 목적/사용 적합한 서비스 설계 |
| 14 | 서비스 데스크 | Service Desk | IT-사용자 간 단일 접점 운영 |
| 15 | 서비스 수준 관리 | Service Level Management | 서비스 수준 목표 설정 및 달성 |
| 16 | 서비스 요청 관리 | Service Request Management | 서비스 요청의 효율적 처리 |
| 17 | 서비스 검증 및 테스트 | Service Validation and Testing | 서비스 품질 요구사항 충족 확인 |

---

## 관련 문서

- [일반 관리 프랙티스](./06-practices-general.md) - 14개 일반 관리 프랙티스
- [기술 관리 프랙티스](./08-practices-technical.md) - 3개 기술 관리 프랙티스
- [핵심 프로세스 심화](./09-key-processes.md) - 주요 프랙티스 상세 워크플로우

---

| 이전 | 다음 |
|------|------|
| [<< 06. 일반 관리 프랙티스](./06-practices-general.md) | [08. 기술 관리 프랙티스 >>](./08-practices-technical.md) |
