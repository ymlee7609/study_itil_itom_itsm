# ITOM 도구 비교

## 목차

1. [주요 ITOM 도구 개요](#1-주요-itom-도구-개요)
2. [통합 플랫폼: ServiceNow ITOM](#2-통합-플랫폼-servicenow-itom)
3. [모니터링 및 관측성 도구](#3-모니터링-및-관측성-도구)
4. [오픈소스 도구](#4-오픈소스-도구)
5. [인시던트 관리 및 온콜 도구](#5-인시던트-관리-및-온콜-도구)
6. [도구 선택 가이드](#6-도구-선택-가이드)
7. [도구 간 연동 패턴](#7-도구-간-연동-패턴)

---

## 1. 주요 ITOM 도구 개요

| 도구 | 유형 | 핵심 기능 | 대상 규모 | 라이선스 |
|------|------|-----------|----------|---------|
| ServiceNow ITOM | 통합 플랫폼 | Discovery, Event Mgmt, Service Mapping, AIOps | 대기업 | 상용 (Enterprise) |
| Datadog | 모니터링/관측성 | 인프라, APM, 로그, 보안, RUM | 중~대기업 | 상용 (SaaS) |
| Splunk | 로그 분석/SIEM | 로그 분석, 이상 탐지, 보안 모니터링 | 중~대기업 | 상용 |
| Nagios | 오픈소스 모니터링 | 네트워크/서버/서비스 모니터링, 알림 | 소~중기업 | 오픈소스/상용 |
| Zabbix | 오픈소스 모니터링 | 인프라 모니터링, 디스커버리, 트리거 | 소~대기업 | 오픈소스 |
| SolarWinds | 네트워크 관리 | 네트워크 성능, 구성, 로그 분석 | 중~대기업 | 상용 |
| New Relic | 관측성 | APM, 인프라, 로그, 합성 모니터링 | 중~대기업 | 상용 (Freemium) |
| AppDynamics | APM | 비즈니스 트랜잭션, 코드 수준 진단 | 대기업 | 상용 (Cisco) |
| PagerDuty | 인시던트 관리 | 온콜, 에스컬레이션, 자동화 | 전 규모 | 상용 (SaaS) |
| ManageEngine OpManager | 네트워크/서버 | 네트워크 모니터링, 대역폭, VM | 소~중기업 | 상용 |

---

## 2. 통합 플랫폼: ServiceNow ITOM

ServiceNow ITOM은 가장 포괄적인 통합 ITOM 플랫폼이다.

### ServiceNow ITOM 모듈 구성

| 모듈 | 핵심 기능 | 설명 |
|------|-----------|------|
| **ITOM Visibility** | Discovery, Service Mapping | IT 환경의 가시성 확보 |
| **ITOM Health** | Event Management, AIOps, Health Log Analytics | IT 건강 상태 관리 |
| **ITOM Optimization** | Cloud Management, Site Reliability Ops | 클라우드 및 운영 최적화 |
| **ITOM Cloud Accelerate** | Cloud Provisioning, Governance | 클라우드 가속화 |

### ITOM Visibility 상세

| 기능 | 설명 | 연계 |
|------|------|------|
| Discovery | 네트워크 스캔, CI 자동 생성 | CMDB 자동 갱신 |
| Service Mapping | 서비스-인프라 관계 자동 매핑 | [변경 영향 분석](../itsm/) |
| Horizontal Discovery | 멀티패턴 디스커버리 | 복잡한 환경 지원 |
| Cloud Discovery | AWS, Azure, GCP 리소스 식별 | 클라우드 CMDB |

### ITOM Health 상세

| 기능 | 설명 | 핵심 가치 |
|------|------|-----------|
| Event Management | 이벤트 수집, 필터링, 상관분석 | 노이즈 90%+ 감소 |
| AIOps (AI Operations) | ML 기반 이상 탐지, 근본 원인 분석 | 자동 인시던트 생성 |
| Health Log Analytics | 로그 수집, 패턴 분석, 이상 탐지 | 사전 장애 예방 |
| Metric Intelligence | 시계열 데이터 분석, 이상 탐지 | 예측 기반 알림 |
| Alert Intelligence | 유사 알림 그룹핑, 중복 제거 | 알림 피로도 감소 |

### ITOM Optimization 상세

| 기능 | 설명 | 효과 |
|------|------|------|
| Cloud Cost Management | 클라우드 비용 분석 및 최적화 | 비용 20-30% 절감 |
| Cloud Provisioning | IaC 기반 자동 프로비저닝 | 배포 시간 단축 |
| Cloud Governance | 정책 기반 클라우드 거버넌스 | 컴플라이언스 확보 |
| Site Reliability Ops | SRE 실천 지원 | SLO 기반 운영 |

---

## 3. 모니터링 및 관측성 도구

### Datadog

| 항목 | 상세 |
|------|------|
| 유형 | 클라우드 네이티브 모니터링/관측성 플랫폼 (SaaS) |
| 핵심 기능 | 인프라 모니터링, APM, 로그 관리, 합성 모니터링, RUM, 보안 |
| 강점 | 700+ 통합, 직관적 UI, 실시간 대시보드, ServiceNow 통합 |
| 약점 | 비용 (대규모 환경), 데이터 보존 비용 |
| 적합 환경 | 클라우드 네이티브, 마이크로서비스, DevOps |

### Splunk

| 항목 | 상세 |
|------|------|
| 유형 | 로그 분석 및 SIEM 플랫폼 |
| 핵심 기능 | 로그 수집/분석, 이상 탐지, 보안 모니터링, SOAR |
| 강점 | 강력한 검색 언어 (SPL), 대규모 로그 처리, 보안 분석 |
| 약점 | 높은 라이선스 비용, 학습 곡선, 리소스 소비 |
| 적합 환경 | 보안 중심 조직, 대규모 로그 분석, 컴플라이언스 |

### New Relic

| 항목 | 상세 |
|------|------|
| 유형 | 풀스택 관측성 플랫폼 |
| 핵심 기능 | APM, 인프라 모니터링, 로그, 합성 모니터링, 브라우저 모니터링 |
| 강점 | Freemium 모델 (100GB/월 무료), 통합 UI, NRQL 쿼리 |
| 약점 | 무료 티어 제한, 일부 고급 기능 유료 |
| 적합 환경 | 스타트업~대기업, APM 중심 |

### AppDynamics

| 항목 | 상세 |
|------|------|
| 유형 | APM 및 비즈니스 관측성 플랫폼 (Cisco) |
| 핵심 기능 | 비즈니스 트랜잭션 추적, 코드 수준 진단, 비즈니스 iQ |
| 강점 | 비즈니스 영향 분석, 자동 베이스라인, 코드 레벨 가시성 |
| 약점 | 높은 비용, 복잡한 설정, 에이전트 오버헤드 |
| 적합 환경 | 대기업, 비즈니스 크리티컬 앱, Java/.NET 환경 |

### SolarWinds

| 항목 | 상세 |
|------|------|
| 유형 | 네트워크 및 IT 인프라 관리 플랫폼 |
| 핵심 기능 | 네트워크 성능 모니터링, 구성 관리, 로그 분석, 패치 관리 |
| 강점 | 네트워크 전문성, 토폴로지 맵, 직관적 UI |
| 약점 | 클라우드 네이티브 지원 제한, 보안 이슈 이력 |
| 적합 환경 | 온프레미스 중심 네트워크 관리 |

---

## 4. 오픈소스 도구

| 비교 항목 | Nagios | Zabbix | Prometheus |
|-----------|--------|--------|------------|
| 라이선스 | GPL v2 | GPL v2 | Apache 2.0 |
| 아키텍처 | 플러그인 기반 | 서버-에이전트 | Pull 기반 시계열 |
| 설정 방식 | 파일 기반 | 웹 UI + API | YAML + PromQL |
| 디스커버리 | 수동/플러그인 | 자동 (네트워크 스캔) | 서비스 디스커버리 |
| 알림 | 이메일, SMS, 플러그인 | 이메일, SMS, 웹훅 | Alertmanager |
| 시각화 | 기본 웹 UI | 내장 대시보드 | Grafana 연동 |
| 확장성 | 보통 | 높음 (프록시 구조) | 높음 (Federation) |
| 학습 곡선 | 높음 | 중간 | 중간~높음 |
| 적합 환경 | 전통 인프라 | 범용 인프라 | 클라우드 네이티브/K8s |
| 커뮤니티 | 큼 (레거시) | 큼 (활발) | 매우 큼 (CNCF) |

### ManageEngine OpManager

| 항목 | 상세 |
|------|------|
| 유형 | 네트워크/서버/VM 모니터링 |
| 핵심 기능 | 네트워크 모니터링, 대역폭 분석, 서버/VM 모니터링, 플로우 분석 |
| 강점 | 합리적 가격, 쉬운 설정, 종합적 기능 |
| 적합 환경 | 소~중기업, 비용 민감 조직 |

---

## 5. 인시던트 관리 및 온콜 도구

| 비교 항목 | PagerDuty | OpsGenie (Atlassian) | VictorOps (Splunk) |
|-----------|-----------|---------------------|-------------------|
| 핵심 기능 | 온콜, 에스컬레이션, 자동화 | 온콜, 알림 라우팅, 팀 협업 | 인시던트 대응, DevOps 통합 |
| 통합 수 | 700+ | 200+ | 100+ |
| 가격 모델 | 사용자당 과금 | 사용자당 과금 | 사용자당 과금 |
| AI/ML | AIOps, 이벤트 인텔리전스 | 기본 노이즈 감소 | 머신러닝 알림 |
| [ITSM 연동](../itsm/) | ServiceNow, Jira | Jira (네이티브) | ServiceNow |
| 강점 | 시장 리더, 풍부한 생태계 | Atlassian 통합 | Splunk/DevOps 통합 |

---

## 6. 도구 선택 가이드

### 조직 규모별 권장

| 조직 규모 | 권장 조합 | 예상 월 비용 |
|-----------|----------|-------------|
| 스타트업 (1-50명) | Zabbix/Prometheus + Grafana + PagerDuty | $500~$2,000 |
| 중소기업 (50-500명) | Datadog/New Relic + PagerDuty + 기본 ITSM | $2,000~$10,000 |
| 중견기업 (500-2,000명) | Datadog + Splunk + ServiceNow ITSM | $10,000~$50,000 |
| 대기업 (2,000명+) | ServiceNow ITOM + Datadog/Splunk + PagerDuty | $50,000+ |

### 요구사항별 권장

| 요구사항 | 최적 도구 | 대안 |
|----------|----------|------|
| 네트워크 모니터링 중심 | SolarWinds, Zabbix | PRTG, ManageEngine |
| 클라우드 네이티브 모니터링 | Datadog | New Relic, Prometheus |
| APM (애플리케이션 성능) | Datadog APM, New Relic | AppDynamics, Dynatrace |
| 로그 분석/보안 | Splunk | ELK Stack, Datadog Logs |
| 통합 ITOM 플랫폼 | ServiceNow ITOM | BMC Helix |
| 비용 최소화 (오픈소스) | Prometheus + Grafana + Zabbix | Nagios, ELK Stack |
| 인시던트/온콜 관리 | PagerDuty | OpsGenie, Grafana OnCall |
| AIOps | ServiceNow AIOps, Moogsoft | BigPanda, Datadog |

### 선택 시 고려사항

| 고려사항 | 질문 | 영향 |
|----------|------|------|
| 환경 유형 | 온프레미스? 클라우드? 하이브리드? | 도구 호환성 |
| 규모 | 모니터링 대상 수? 데이터 양? | 라이선스 비용, 확장성 |
| 기존 도구 | 현재 사용 중인 도구? | 통합/마이그레이션 비용 |
| 팀 역량 | 운영팀 기술 수준? | 학습 곡선, 지원 필요성 |
| 예산 | 초기 투자? 운영 비용? | 상용 vs 오픈소스 결정 |
| 컴플라이언스 | 규제 요구사항? 데이터 주권? | SaaS vs 온프레미스 결정 |

---

## 7. 도구 간 연동 패턴

### 일반적인 연동 아키텍처

| 연동 패턴 | 소스 도구 | 대상 도구 | 데이터/이벤트 |
|-----------|----------|----------|-------------|
| 모니터링 → 알림 | Datadog/Zabbix | PagerDuty | 경보/이벤트 |
| 모니터링 → ITSM | Datadog/Nagios | ServiceNow | [인시던트 자동 생성](../itsm/) |
| 로그 → 분석 | Fluentd/Filebeat | Splunk/ELK | 로그 데이터 |
| ITOM → CMDB | ServiceNow Discovery | ServiceNow CMDB | CI 데이터 |
| 모니터링 → 시각화 | Prometheus | Grafana | 메트릭 |
| APM → 트레이싱 | Datadog APM | Datadog/Jaeger | 트레이스 |

### 데이터 표준 및 프로토콜

| 표준/프로토콜 | 용도 | 지원 도구 |
|-------------|------|----------|
| SNMP (Simple Network Management Protocol) | 네트워크 장비 모니터링 | Zabbix, Nagios, SolarWinds |
| OpenTelemetry (OTel) | 통합 관측성 데이터 수집 | Datadog, New Relic, Jaeger |
| Syslog | 로그 전송 표준 | Splunk, ELK, Zabbix |
| Prometheus Remote Write | 메트릭 전송 | Prometheus, Datadog, Grafana |
| Webhook | 이벤트 알림 | 대부분의 도구 |
| REST API | 양방향 데이터 연동 | 대부분의 도구 |

---

## 참고

- ITOM 핵심 역량에 대한 상세 내용은 [03-capabilities.md](./03-capabilities.md) 참조
- AIOps 및 트렌드는 [05-aiops-trends.md](./05-aiops-trends.md) 참조
- ITSM 도구와의 통합은 [ITSM 문서](../itsm/) 참조

---

| 이전 | 다음 |
|------|------|
| [← ITOM 핵심 역량](./03-capabilities.md) | [AIOps 및 ITOM 트렌드 →](./05-aiops-trends.md) |
