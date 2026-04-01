# ITOM (IT Operations Management) 개요

## 목차

1. [ITOM 정의](#1-itom-정의)
2. [IT 운영 관리의 범위](#2-it-운영-관리의-범위)
3. [3대 핵심 기능](#3-3대-핵심-기능)
4. [ITOM의 비즈니스 가치](#4-itom의-비즈니스-가치)
5. [ITOM과 ITIL 4의 관계](#5-itom과-itil-4의-관계)
6. [ITOM 성숙도 모델](#6-itom-성숙도-모델)

---

## 1. ITOM 정의

**ITOM (IT Operations Management)**은 IT 인프라의 **프로비저닝 (Provisioning)**, **용량 (Capacity)**, **성능 (Performance)**, **가용성 (Availability)**을 체계적으로 관리하는 전략적 접근 방식이다.

| 항목 | 설명 |
|------|------|
| 정의 | IT 인프라와 서비스의 운영을 최적화하기 위한 프로세스, 도구, 기술의 집합 |
| 목적 | 안정적이고 효율적인 IT 운영 환경 구축 및 유지 |
| 대상 | 서버, 네트워크, 스토리지, 클라우드, 애플리케이션, 엔드포인트 |
| 핵심 원칙 | 자동화, 가시성 (Visibility), 예측 기반 운영 (Proactive Operations) |

### ITOM이 필요한 이유

| 과제 | ITOM 없이 | ITOM 도입 후 |
|------|-----------|-------------|
| 장애 대응 | 사후 대응 (Reactive) | 사전 예방 (Proactive) |
| 인프라 파악 | 수동 문서화, 정보 부족 | 자동 디스커버리, 실시간 현황 |
| 용량 계획 | 경험 기반 추정 | 데이터 기반 예측 분석 |
| 서비스 영향 분석 | 불가능 또는 부정확 | 서비스 매핑 기반 정확한 분석 |
| 비용 관리 | 과잉 프로비저닝 | 최적 리소스 할당 |

---

## 2. IT 운영 관리의 범위

ITOM은 IT 환경의 모든 계층을 관리 대상으로 포함한다.

| 관리 영역 | 구성 요소 | 주요 활동 |
|-----------|-----------|-----------|
| 디지털 서비스 (Digital Services) | 웹 서비스, API, SaaS | 서비스 가용성 모니터링, SLA 관리 |
| 기술 인프라 (Technology) | 서버, 네트워크, 스토리지, 클라우드 | 프로비저닝, 용량 관리, 성능 최적화 |
| 구성요소 (Components) | OS, 미들웨어, 데이터베이스 | 패치 관리, 구성 관리, 컴플라이언스 |
| 애플리케이션 (Applications) | 비즈니스 앱, 사내 시스템 | APM, 로그 분석, 트랜잭션 추적 |

### IT 운영 관리 계층 구조

```
비즈니스 서비스 (Business Services)
    └── 디지털 서비스 (Digital Services)
        └── 애플리케이션 (Applications)
            └── 미들웨어/플랫폼 (Middleware/Platform)
                └── 인프라 (Infrastructure)
                    ├── 컴퓨팅 (Compute)
                    ├── 네트워크 (Network)
                    └── 스토리지 (Storage)
```

---

## 3. 3대 핵심 기능

### 3.1 네트워크 인프라 관리 (Network Infrastructure Management)

| 항목 | 상세 |
|------|------|
| 정의 | 네트워크 서비스 및 관련 하드웨어/소프트웨어의 프로비저닝, 모니터링, 유지보수 |
| 대상 | 라우터, 스위치, 방화벽, 로드밸런서, VPN, SD-WAN |
| 주요 활동 | 네트워크 성능 모니터링, 트래픽 분석, 장애 탐지, 용량 계획 |
| 도구 예시 | SolarWinds, Nagios, Zabbix, PRTG |

**세부 기능:**

| 기능 | 설명 |
|------|------|
| 네트워크 모니터링 (Network Monitoring) | 대역폭, 지연시간, 패킷 손실 등 실시간 측정 |
| 트래픽 분석 (Traffic Analysis) | 네트워크 흐름 패턴 분석 및 이상 탐지 |
| 구성 관리 (Configuration Management) | 네트워크 장비 설정 백업, 변경 추적, 컴플라이언스 |
| 장애 관리 (Fault Management) | 자동 장애 탐지, 알림, 에스컬레이션 |

### 3.2 헬프데스크 운영 (Help Desk Operations)

| 항목 | 상세 |
|------|------|
| 정의 | IT 서비스 사용자에 대한 지원 및 운영 요청 처리 |
| 핵심 프로세스 | 인시던트 대응, 이벤트 대응, 요청 이행 |
| 연계 영역 | ITSM 서비스 데스크와의 통합 |
| 도구 예시 | ServiceNow, Jira Service Management, Zendesk |

**핵심 프로세스 비교:**

| 프로세스 | 트리거 | 목표 | ITIL 4 연계 |
|----------|--------|------|------------|
| 인시던트 대응 (Incident Response) | 서비스 중단/저하 | 신속한 서비스 복구 | [인시던트 관리](../itil4/01-overview.md) |
| 이벤트 대응 (Event Response) | 모니터링 경고 | 사전 예방적 조치 | 모니터링 및 이벤트 관리 |
| 요청 이행 (Request Fulfillment) | 사용자 요청 | 표준 서비스 제공 | 서비스 요청 관리 |

### 3.3 엔드포인트 관리 (Endpoint Management)

| 항목 | 상세 |
|------|------|
| 정의 | 조직 내 모든 엔드포인트 장치의 프로비저닝, 보안, 유지보수 |
| 대상 | 서버, 데스크톱, 노트북, 모바일 기기, IoT 디바이스 |
| 주요 활동 | OS 배포, 패치 관리, 소프트웨어 배포, 보안 정책 적용 |
| 도구 예시 | Microsoft Intune, SCCM, Jamf, ManageEngine |

**엔드포인트 유형별 관리 포인트:**

| 엔드포인트 유형 | 관리 포인트 | 보안 고려사항 |
|----------------|------------|--------------|
| 서버 (Server) | 패치, 모니터링, 백업, 용량 | 접근 제어, 취약점 관리 |
| 데스크톱 (Desktop) | OS, 소프트웨어, 설정 | 엔드포인트 보호, 데이터 암호화 |
| 모바일 (Mobile) | MDM, 앱 관리, 원격 삭제 | BYOD 정책, 컨테이너화 |
| IoT | 펌웨어 업데이트, 네트워크 분리 | 인증, 통신 암호화 |

---

## 4. ITOM의 비즈니스 가치

| 가치 영역 | 설명 | 측정 지표 (KPI) |
|-----------|------|----------------|
| 안정성 (Reliability) | 서비스 중단 감소, 고가용성 확보 | MTTR, MTBF, 가용성 (%) |
| 효율성 (Efficiency) | 자동화를 통한 운영 효율 향상 | 자동화율, 처리 시간 |
| 비용 최적화 (Cost Optimization) | 리소스 활용도 향상, 낭비 감소 | TCO, 클라우드 비용, 라이선스 최적화 |
| 가시성 (Visibility) | IT 환경 전체에 대한 통합 가시성 | CMDB 정확도, 서비스 맵 완성도 |
| 컴플라이언스 (Compliance) | 규정 준수 자동화 | 감사 통과율, 정책 준수율 |
| 민첩성 (Agility) | 신속한 변경 및 배포 지원 | 배포 빈도, 변경 리드타임 |

### ROI 사례

| 항목 | 도입 전 | 도입 후 | 개선율 |
|------|---------|---------|--------|
| 평균 복구 시간 (MTTR) | 4시간 | 30분 | 87% |
| 월간 장애 건수 | 15건 | 3건 | 80% |
| 수동 작업 시간 | 주 40시간 | 주 8시간 | 80% |
| 클라우드 비용 | 월 $50,000 | 월 $35,000 | 30% |

---

## 5. ITOM과 ITIL 4의 관계

ITOM은 [ITIL 4 프레임워크](../itil4/01-overview.md)의 여러 관리 실천(Management Practices)과 밀접하게 연관된다.

| ITIL 4 실천 (Practice) | ITOM 관련성 | 관계 |
|------------------------|------------|------|
| 모니터링 및 이벤트 관리 (Monitoring and Event Management) | 핵심 | ITOM의 근간 |
| 인프라 및 플랫폼 관리 (Infrastructure and Platform Management) | 핵심 | ITOM 범위와 동일 |
| 배포 관리 (Deployment Management) | 높음 | 자동화 배포 지원 |
| IT 자산 관리 (IT Asset Management) | 높음 | 디스커버리 연계 |
| 정보 보안 관리 (Information Security Management) | 중간 | 보안 모니터링 |
| 가용성 관리 (Availability Management) | 높음 | 가용성 측정/보장 |
| 용량 및 성능 관리 (Capacity and Performance Management) | 핵심 | ITOM 핵심 기능 |

---

## 6. ITOM 성숙도 모델

| 수준 | 단계 | 특징 | 주요 활동 |
|------|------|------|-----------|
| 1 | 초기 (Initial) | 수동, 반응적 | 개별 도구 사용, 문서화 부족 |
| 2 | 관리 (Managed) | 기본 모니터링 | 알림 설정, 기본 대시보드 |
| 3 | 정의 (Defined) | 표준화된 프로세스 | 통합 모니터링, CMDB, 서비스 맵 |
| 4 | 측정 (Measured) | 데이터 기반 운영 | KPI 측정, 트렌드 분석, 자동화 |
| 5 | 최적화 (Optimized) | AI/ML 기반 자율 운영 | AIOps, 예측 분석, 자동 복구 |

---

## 참고

- ITOM과 ITSM의 차이점에 대한 자세한 비교는 [02-itom-vs-itsm.md](./02-itom-vs-itsm.md) 참조
- ITOM 핵심 역량에 대한 상세 내용은 [03-capabilities.md](./03-capabilities.md) 참조
- ITIL 4 개요는 [ITIL 4 개요](../itil4/01-overview.md) 참조

---

| 이전 | 다음 |
|------|------|
| - | [ITOM vs ITSM 비교 →](./02-itom-vs-itsm.md) |
