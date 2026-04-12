# ServiceNow Knowledge 2026 개요

| 항목 | 내용 |
|------|------|
| **문서 성격** | Knowledge 2026 사전 공개 정보 기반 프리뷰 (컨퍼런스 후 업데이트 예정) |
| **작성일** | 2026-04-13 |
| **최종 업데이트** | 2026-04-13 |
| **상태** | 프리뷰 (사전 공개 기반, 컨퍼런스 후 업데이트 필요) |

---

## 행사 개요

| 항목 | 내용 |
|------|------|
| **행사명** | ServiceNow Knowledge 2026 |
| **일정** | 2026년 5월 5일~7일 (3일간) |
| **장소** | Venetian Resort & Wynn Las Vegas, 미국 라스베이거스 |
| **규모** | ServiceNow 최대 규모 연례 컨퍼런스 |
| **구성** | 키노트, 1,000+ 브레이크아웃 세션, CreatorCon, 기술 교육 |
| **키노트** | Bill McDermott (ServiceNow CEO) |
| **특별 게스트** | Idris Elba (배우, 인사이트 세션 + DJ 공연) |
| **등록** | [공식 등록 페이지](https://www.servicenow.com/events/knowledge.html) |

---

## 핵심 발표 영역 (사전 공개 기반)

### 1. AI Agents & Agent Studio

Knowledge 2026의 가장 큰 테마는 **AI 에이전트**입니다. 단순 챗봇을 넘어 업무를 자율적으로 수행하는 AI 에이전트를 Now Platform 위에서 구축·운영하는 방향을 제시합니다.

| 기능 | 설명 |
|------|------|
| **Agent Studio** | AI 에이전트의 행동 방식을 정의하는 도구. 모호한 지시가 아닌 명확한 임무·경계·제한을 설정 |
| **AI Control Tower** | AI 에이전트의 거버넌스 도구. "Black Box AI"를 투명하고 통제 가능한 자산으로 전환 |
| **RaptorDB Professional** | 데이터 쿼리 속도 27배 향상. AI 에이전트가 트랜잭션 진행 중에도 실시간 데이터 조회 가능 |

**시리즈 연결**: Part 6에서 다룬 ITIL 5의 AI 거버넌스(6C 모델)와 COBIT의 거버넌스 관점이 AI Control Tower와 맞닿습니다. "AI를 어떻게 책임감 있게 도입할 것인가"에 대한 ServiceNow의 구체적 제품 답변입니다.

### 2. 산업별 솔루션 강화

Knowledge 2026에서 산업별 특화 솔루션이 더 강화됩니다. 특히 통신, 금융, 공공 분야가 핵심입니다.

| 산업 | 주요 테마 |
|------|---------|
| **통신 (Telecom)** | TSM/TSOM 고도화, 네트워크→고객 단일 플랫폼, AI 기반 서비스 보증 |
| **금융 (Banking)** | Digital → Agentic 전환, AI Control Tower 금융 규제 대응 |
| **공공 (Government)** | 시민 서비스, 디지털 정부 |

### 3. 통신사 트랙 — TSM & TSOM

Knowledge 2026의 통신사(Telecom) 세션에서 다루는 핵심 주제입니다.

#### TSM (Telecommunications Service Management)

| 주제 | 설명 |
|------|------|
| **단일 AI 플랫폼** | 서비스·네트워크 운영을 하나의 AI 플랫폼에서 통합 |
| **TMF 표준 API 확장** | TMF Open API(620, 621, 633, 637 등) 기반 생태계 연동 강화 |
| **고객 케어 자동화** | Now Assist와 통합된 상담 자동화, Virtual Agent 고도화 |
| **서비스 주문 이행** | Order Management for Telecom (OMT) 기반 자동 프로비저닝 |
| **에이전트 워크스페이스** | 상담사 통합 화면에 AI 인사이트·고객 영향·네트워크 상태 통합 표시 |

#### TSOM (Telecommunications Service Operations Management)

| 주제 | 설명 |
|------|------|
| **서비스 보증(Assurance) 자동화** | 네트워크 이벤트 상관 분석 + 고객 영향 자동 매핑 |
| **5G/IoT 네트워크 관리** | 5G 네트워크 슬라이싱, IoT 디바이스 대규모 관리 |
| **OSS/BSS 사일로 통합** | 기존 OSS/BSS 시스템과의 연동을 단일 플랫폼으로 통합 |
| **TMF Alarm API** | TM Forum 알람 관리 API 기반 멀티 벤더 모니터링 통합 |
| **AIOps 고도화** | 알림 노이즈 감소, 근본 원인 자동 추론, MTTR 단축 |

#### TSM + TSOM 통합 시나리오

통신사 트랙의 핵심 메시지는 **"네트워크에서 고객까지 단일 플랫폼으로 연결"**입니다.

```
네트워크 → TSOM (감지·분석) → TSM (고객 대응) → 현장(FSM)
     ↑                                              |
     └──────────── 피드백 루프 ──────────────────────┘
```

이것은 Part 5에서 다룬 "ITOM → ITSM 자동 연결"의 통신사 전용 확장이며, Part 8 Q&A Q-002에서 정리한 TSM/TSOM 관계가 실제 제품으로 구현되는 모습입니다.

#### TPSM 리브랜딩

Knowledge 2026에서 TSM → **TPSM(Technology Provider Service Management)** 리브랜딩이 공식화될 가능성이 있습니다. "통신사(Telecom)"를 넘어 "기술 제공자(Technology Provider)" 전체로 적용 범위를 확장하는 방향입니다. 다만 실무에서는 여전히 TSM/TSOM으로 통용될 것으로 보입니다.

### 4. Agentic AI와 기존 AI의 차이

Knowledge 2026에서 강조되는 **Agentic AI**는 기존 생성형 AI와 구분됩니다.

| 구분 | 기존 생성형 AI (Now Assist) | Agentic AI (Agent Studio) |
|------|---------------------------|--------------------------|
| **방식** | 사용자 요청 → AI 응답 | AI가 자율적으로 태스크 수행 |
| **범위** | 텍스트 요약, 추천, 분류 | 워크플로우 실행, 의사결정, 자동 처리 |
| **제어** | 프롬프트 기반 | 임무 경계(guardrails) 기반 |
| **거버넌스** | 사용자 판단에 의존 | AI Control Tower가 자동 감시 |
| **적용 예** | 인시던트 요약, 지식 추천 | 티켓 자동 분류·배정·해결, 변경 자동 승인 |

### 5. RaptorDB — 데이터 성능 혁신

| 항목 | 내용 |
|------|------|
| **제품명** | RaptorDB Professional |
| **핵심 개선** | 기존 대비 데이터 쿼리 속도 **27배 향상** |
| **의미** | AI 에이전트가 트랜잭션 진행 중에도 실시간 데이터 조회·판단 가능 |
| **영향** | 대규모 CMDB 조회, 실시간 SLA 계산, AIOps 상관 분석 성능 개선 |

---

## 시리즈와의 연결

| Knowledge 2026 주제 | 시리즈 연결 |
|--------------------|-----------|
| TSM/TSOM 통합 | Part 5 (ITSM↔ITOM 연결), Part 8 Q-002 |
| AI Control Tower | Part 5 (ITIL 5 AI 거버넌스 6C), Part 6 (COBIT 거버넌스) |
| Agent Studio | Part 5 (Now Assist), Part 3 (AIOps) |
| RaptorDB | Part 5 (CMDB 허브), Part 3 (실시간 이벤트 분석) |
| 산업별 솔루션 강화 | Part 7 (통신사 레퍼런스) |
| Agentic AI | Part 7 BT "Zero Ops" 비전의 구체적 도구 |

---

## 주의사항

> **이 문서는 2026년 4월 13일 시점의 사전 공개 정보를 기반으로 작성되었습니다.** Knowledge 2026은 2026년 5월 5~7일에 개최됩니다. 컨퍼런스 후 실제 발표 내용, 신규 기능 GA(General Availability) 일정, 가격 정책 등을 업데이트할 예정입니다.

---

## 약어 정리

| 약어 | 풀네임 | 설명 |
|------|--------|------|
| **TSM** | Telecommunications Service Management | ServiceNow 통신사 전용 서비스 관리 |
| **TSOM** | Telecommunications Service Operations Management | ServiceNow 통신사 전용 운영 관리 |
| **TPSM** | Technology Provider Service Management | TSM의 리브랜딩 명칭 |
| **OMT** | Order Management for Telecom | 통신 주문 관리 |
| **TMF** | TM Forum | 통신 산업 표준화 기구 |
| **OSS/BSS** | Operations/Business Support System | 운영/비즈니스 지원 시스템 |
| **GA** | General Availability | 정식 출시 |
| **NOC** | Network Operations Center | 네트워크 운영 센터 |

---

## 출처

- [ServiceNow Knowledge 2026 공식 페이지](https://www.servicenow.com/events/knowledge.html)
- [What's Happening at Knowledge 2026](https://www.servicenow.com/events/knowledge/happening.html)
- [Knowledge 2026 FAQ](https://www.servicenow.com/events/knowledge/faq.html)
- [Knowledge 2026 Banking Roadmap (ServiceNow Community)](https://www.servicenow.com/community/financial-services-special/servicenow-knowledge-2026-roadmap-for-banking-leaders-from/ta-p/3508192)
- [TSM 공식 제품 페이지](https://www.servicenow.com/products/telecommunications-service-management.html)
- [TSOM 공식 제품 페이지](https://www.servicenow.com/products/telecommunications-service-operations.html)
- [NTT DATA Knowledge 2026 페이지](https://services.global.ntt/en-us/events/servicenow-knowledge-2026)

---

## 변경 이력

| 일자 | 변경 내용 |
|------|---------|
| 2026-04-13 | 최초 작성 (프리뷰, 사전 공개 기반) |
| (예정) 2026-05-07 이후 | 컨퍼런스 실제 발표 내용 반영 업데이트 |
