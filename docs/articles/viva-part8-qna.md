ITSM/ITOM/ITAM 시리즈 Part 8 — Q&A 모음 (지속 업데이트)

**이 문서의 성격**

Part 1~7을 공유하면서 받은 구체적인 질문들을 모은 Q&A 문서입니다. 한 번에 완성된 글이 아니라 **지속적으로 추가되는 누적 문서**입니다. 새로운 질문이 들어올 때마다 이 문서에 섹션을 추가합니다.

- 최초 작성: 2026-04-09
- 최종 업데이트: 2026-04-13

**업데이트 규칙**

- 신규 질문은 Q-NNN 번호로 가장 아래에 추가합니다.
- 각 질문의 답변 말미에 변경 이력을 기록합니다.
- 외부 자료 인용 시 반드시 출처를 표기합니다.
- 시리즈 Part 번호로 관련 링크를 연결합니다.

**질문 목록**

- **Q-001** — ITOM의 RCA와 ITSM의 RCA는 어떻게 다르고 어떻게 연결되는가? (Part 2, 3, 5 관련, 2026-04-09 추가)
- **Q-002** — ServiceNow의 TSM과 TSOM은 뭐가 다르고, ITSM/ITOM과는 어떤 관계인가? (Part 2, 3, 5, 7 관련, 2026-04-13 추가)


**Q-001. ITOM의 RCA와 ITSM의 RCA는 어떻게 다르고 어떻게 연결되는가?**

관련 Part: Part 2 ITSM (문제 관리), Part 3 ITOM (AIOps), Part 5 ServiceNow
추가일: 2026-04-09

**한 줄 요약**

두 RCA는 **같은 이름, 다른 층위**입니다. 경쟁 관계가 아니라 **시간·깊이·주체가 다른 보완 관계**이며, 통합 플랫폼에서는 자동으로 연결됩니다.

**ITOM의 RCA는 "무엇이 고장났는지(What)"를 기계가 즉시 찾고, ITSM의 RCA는 "왜 그렇게 고장날 수밖에 없었는지(Why)"를 사람이 사후에 파헤칩니다.**


**두 RCA의 성격 비교**

- **질문** — ITOM RCA는 "지금 어느 컴포넌트가 고장났는가?"를, ITSM RCA는 "왜 이 장애가 생겼고, 어떻게 재발을 막을 것인가?"를 묻습니다.
- **수행 주체** — ITOM RCA는 시스템(AIOps, Event Correlation Engine)이, ITSM RCA는 사람(Problem Manager, SME, 엔지니어)이 수행합니다.
- **분석 대상** — ITOM RCA는 인프라·네트워크·애플리케이션의 기술적 원인 체인을, ITSM RCA는 기술과 프로세스, 사람, 조직·의사결정까지 포함합니다.
- **입력 데이터** — ITOM RCA는 메트릭·로그·트레이스·이벤트·CMDB 토폴로지를, ITSM RCA는 인시던트 이력·ITOM RCA 결과·변경 기록·인터뷰를 사용합니다.
- **기법** — ITOM RCA는 토폴로지 기반 추론, 시계열 상관, ML 이상 탐지를 사용합니다. ITSM RCA는 5 Why, Ishikawa(생선뼈), Kepner-Tregoe, FMEA 같은 정성적 기법을 사용합니다.
- **시간 축** — ITOM RCA는 실시간~분 단위, ITSM RCA는 시간~일·주 단위입니다.
- **산출물** — ITOM RCA는 상관관계 분석, 용의 CI 리스트, 알림 압축, 자동 티켓 첨부입니다. ITSM RCA는 문제 레코드, Known Error(KEDB), RFC, 교훈 보고서입니다.
- **프로세스 위치** — ITOM RCA는 Event Management / Incident Management 내부에, ITSM RCA는 Problem Management라는 별도 프로세스에 위치합니다.
- **반복 지향** — ITOM RCA는 현재 장애 해결 지원, ITSM RCA는 미래 재발 방지입니다.


**실제 시나리오 — 통신사 월요일 아침 빌링 장애**

**09:12 — ITOM RCA의 시간**

분 단위로 경보가 튀어나옵니다.

- 09:12:03 — CPU 임계치 초과 경보 (billing-app-03)
- 09:12:05 — DB 응답 시간 2.8초 초과 (billing-db-01)
- 09:12:07 — 상담 앱 5xx 에러 급증 (crm-web-02)
- 09:12:08 — Event Correlation 엔진이 세 경보를 "billing 서비스 토폴로지"로 묶고, 용의 CI를 billing-db-01로 지목합니다. 인시던트가 자동 생성되고(INC-20260406-0142), 우선순위는 P1(영향도 200명)으로 자동 판정됩니다.

ITOM이 한 일은 분 단위로 기술 원인 체인을 자동 추론해 "billing-db-01이 용의자"라고 지목한 것입니다. 한계는 "그래서 왜 월요일마다 그러는지"는 대답하지 못한다는 점입니다.

**10:30 — 복구 후 ITSM RCA의 시간**

서비스는 DB 재시작으로 복구되었지만 동일 패턴이 3주 연속 발생. ITSM의 문제 관리가 발동합니다. Problem Record PRB-20260406-0019가 생성되고, 입력으로 INC-0142 외 동일 패턴 인시던트 3건을 받습니다. 기법은 5 Why입니다.

- Q1. 왜 DB가 월요일 아침에 느려지나? → A1. 메모리와 커넥션 풀이 꽉 차 있었음
- Q2. 왜 메모리가 꽉 찼나? → A2. 주말 배치 작업이 남긴 세션이 정리되지 않았음
- Q3. 왜 세션이 정리되지 않았나? → A3. 배치 실패 시 finally 블록에서 close()가 누락돼 있음
- Q4. 왜 코드에 누락이 있었나? → A4. 코드 리뷰에서 예외 경로 검토가 빠졌음
- Q5. 왜 리뷰 체크리스트에 예외 경로가 없었나? → A5. 팀 리뷰 가이드가 최신 아키텍처를 반영하지 못함

근본 원인은 **리뷰 가이드의 노후화(프로세스 결함)**입니다. 해결책은 배치 코드 finally 수정(RFC)과 리뷰 체크리스트 개정이고, KEDB 등록 후 변경 관리로 연결됩니다.

ITSM RCA가 한 일은 ITOM이 던진 "billing-db-01"이라는 단서를 받아서 **기술 → 프로세스 → 조직**으로 "왜"를 계속 파고든 것입니다. 도달한 지점은 코드 수정 하나가 아니라 **리뷰 가이드 개정**이라는 프로세스 개선까지입니다.


**관계의 핵심 네 가지**

- **시간축** — ITOM RCA는 "지금" 대응(분·시간 단위), ITSM RCA는 "이후" 분석(일·주 단위)입니다.
- **입력-출력** — ITOM RCA가 남긴 상관관계·토폴로지·타임라인이 ITSM RCA의 가장 신뢰도 높은 입력이 됩니다. ITOM 없이 ITSM만 하면 "감으로 하는 추정"이 됩니다.
- **깊이 방향** — ITOM은 수직적으로 깊이 탐색(서버 → DB → 네트워크), ITSM은 수평적으로 원인 확장(코드 → 리뷰 → 가이드 → 교육 → 조직 문화)입니다.
- **목적 지표** — ITOM은 MTTR 단축, ITSM은 재발률 감소를 봅니다. 둘 다 필요합니다. MTTR만 쫓으면 같은 장애가 반복되고, 재발 방지만 쫓으면 현재 장애를 못 끕니다.


**통합 플랫폼(ServiceNow 기준)에서의 자동 연계**

Part 5에서 다룬 단일 플랫폼 전략이 이 관계를 자동화합니다.

- 1단계 감지 — ITOM Event Management가 메트릭·로그·이벤트를 수집하고 이상을 감지합니다.
- 2단계 상관 분석 — ITOM Event Management와 AIOps가 토폴로지 기반 상관 분석을 수행하고 용의 CI를 지목합니다.
- 3단계 인시던트 생성 — ITSM Incident Management에서 상관 결과가 자동 첨부된 티켓이 생성됩니다.
- 4단계 복구 — ITSM Incident Management에서 런북·KEDB·지식베이스를 검색하고 담당자를 배정합니다.
- 5단계 패턴 감지 — ITSM Problem Management가 반복 인시던트를 자동 탐지해 문제 레코드를 생성합니다.
- 6단계 근본 원인 분석 — ITSM Problem Management에서 사람이 5 Why, Ishikawa 등으로 분석합니다.
- 7단계 재발 방지 — ITSM Change Enablement에서 RFC를 생성하고 CAB 승인 후 변경을 구현합니다.
- 8단계 피드백 검증 — ITOM Event Management가 변경 후 메트릭 개선 여부를 다시 측정합니다.

8단계의 피드백 루프가 핵심입니다. ITSM RCA의 결론을 ITOM이 다시 측정해서 "진짜 해결됐는지" 확인해야 RCA 사이클이 완결됩니다. 이걸 안 하는 조직이 많은데, 하지 않으면 "보고서만 만들고 실제 개선은 없었던" 사태가 반복됩니다.


**의료 비유로 이해하기**

- **장비** — ITOM RCA는 CT, MRI, 혈액 검사 같은 장비입니다. ITSM RCA는 문진, 생활 습관 조사, 가족력 파악입니다.
- **질문** — ITOM RCA는 "어느 장기에 문제가 있는가?"를 묻습니다. ITSM RCA는 "왜 이 환자가 이 병에 걸렸는가?"를 묻습니다.
- **시간** — ITOM RCA는 응급실에서 수십 분 안에, ITSM RCA는 주치의 진료실에서 며칠~몇 주에 걸쳐 이루어집니다.
- **결과** — ITOM RCA는 병변 위치 특정과 응급 처치, ITSM RCA는 생활 습관 개선과 치료 계획입니다.

응급 환자가 오면 CT부터 찍지 문진부터 하지 않습니다. 반대로 퇴원만 시키고 생활 습관 개선을 안 하면 한 달 뒤에 또 실려 옵니다. 두 RCA가 공존해야 하는 이유입니다.


**자주 나타나는 안티패턴**

- **ITOM RCA만 있는 조직** — 매번 빨리 복구는 되지만 같은 장애가 반복됩니다. Problem Management 도입과 ITOM 데이터를 입력으로 활용하는 것이 해결책입니다.
- **ITSM RCA만 있는 조직** — 사후 보고서는 많은데 장애 대응이 느립니다. Event Correlation, AIOps 도입이 필요합니다.
- **둘이 단절된 조직** — ITOM의 상관 분석 결과가 Problem Record에 연결되지 않습니다. 단일 플랫폼 또는 API 연동, CMDB 공유가 해결책입니다.
- **RCA가 사람 탓으로 끝남** — "누가 실수했나"로 귀결됩니다. 5 Why를 끝까지 — 프로세스·시스템 원인까지 도달해야 합니다.


**시리즈 내 위치**

- Part 2 문제 관리 — ITSM RCA의 프로세스적 관점
- Part 3 ITOM / AIOps — ITOM RCA의 기술적 관점
- Part 5 ServiceNow — 두 RCA를 하나의 플랫폼에서 자동 연결하는 구조
- Part 6 거버넌스 — RCA 결과를 리스크 등록부·감사 추적으로 연결 (COBIT MEA03)
- Part 7 BT 사례 — Customer Ops → AI Ops → Zero Ops 진화 모델이 이 연계를 단계별로 성숙시키는 로드맵

두 RCA는 따로 존재하는 두 기능이 아니라, **하나의 장애 대응 생애주기에서 시간을 두고 이어지는 두 단계**입니다. 통신사처럼 장애 빈도와 영향 범위가 큰 환경에서는 이 연계의 자동화 수준이 곧 운영 성숙도를 결정합니다.

**변경 이력**

- 2026-04-09 — 최초 작성


**Q-002. ServiceNow의 TSM과 TSOM은 뭐가 다르고, ITSM/ITOM과는 어떤 관계인가?**

관련 Part: Part 2 ITSM, Part 3 ITOM, Part 5 ServiceNow, Part 7 통신사 사례
추가일: 2026-04-13

**한 줄 요약**

TSM과 TSOM은 둘 다 ServiceNow의 통신사(CSP) 전용 제품이지만 역할이 다릅니다. **TSM은 통신사의 "홀 서비스"(고객 대응·서비스 전달), TSOM은 "주방 운영"(네트워크 감시·장애 대응)**입니다. Part 5에서 설명한 ITSM과 ITOM의 관계를 통신사 맥락으로 확장한 것이라 보면 됩니다.

**TSM (Telecommunications Service Management)**

- 공식 정의: ITSM + CSM + KM + FSM + Telco Knowledge의 조합입니다.
- 핵심 질문: "고객 문의·주문·장애 신고를 어떻게 처리할 것인가?"
- 주요 기능: 옴니채널 접수, 에이전트 워크스페이스, 서비스 주문 이행, SLA 관리, TMF 표준 API(620, 621, 633, 637 등)
- 대응하는 일반 제품: ITSM + CSM(Customer Service Management)
- 사용자: 고객센터 상담사, 서비스 매니저, 현장 기사

**TSOM (Telecommunications Service Operations Management)**

- 공식 정의: ITOM + 통신 특화 서비스 보증입니다.
- 핵심 질문: "네트워크·서비스 건강 상태를 어떻게 감시하고 대응할 것인가?"
- 주요 기능: 이벤트 상관 분석, 서비스 보증(Assurance), 장애 관리, 고객 영향 매핑, AIOps
- 대응하는 일반 제품: ITOM(Health + Visibility)
- 사용자: NOC(Network Operations Center) 엔지니어, 운영팀

**왜 둘 다 필요한가**

고객이 "인터넷이 안 돼요"라고 전화합니다. TSM이 옴니채널로 접수하고 에이전트 워크스페이스에서 서비스 영향을 확인하고 티켓을 생성합니다. 그 순간 TSOM에 "이 고객에게 영향 주는 네트워크 이벤트가 있나?" 쿼리가 갑니다. TSOM이 이벤트 상관 분석으로 "OLT-강남-03 장애, 영향 고객 1,247명"이라는 결과를 돌려줍니다. 다시 TSM이 현장 기사를 디스패치하고, 복구 확인 후 고객에게 안내하고 티켓을 닫습니다.

- TSM만 있으면 — 고객 전화는 받지만 "지금 네트워크에서 뭐가 문제인지" 모릅니다.
- TSOM만 있으면 — 네트워크 장애는 감지하지만 "어떤 고객에게 영향을 주는지" 모릅니다.
- 둘이 연결되면 — TSOM이 감지한 네트워크 이벤트가 TSM의 고객 티켓에 자동 매핑되고, 영향 고객 수가 즉시 산출됩니다.

이것이 Part 5에서 강조한 ITSM ↔ ITOM 자동 연결의 통신사 전용 버전입니다.

**ITSM/ITOM과의 매핑**

- ITSM → TSM으로 확장됩니다. TMF 표준 API, 서비스 주문 이행(Order Management for Telecom), 통신 특화 카탈로그가 추가됩니다.
- ITOM → TSOM으로 확장됩니다. 통신 네트워크 토폴로지 이해, TMF Alarm API, 5G/IoT/OSS/BSS 연동, 서비스 보증이 추가됩니다.
- CSM은 TSM에 내포됩니다. 통신사 고객 여정에 특화된 워크플로우가 들어갑니다.
- FSM도 TSM에 내포됩니다. 현장 기사 디스패치, 통신 장비 설치·복구가 포함됩니다.

**Q-001 RCA와의 연결**

Q-001에서 다뤘던 "ITOM RCA → ITSM RCA" 관계가 통신사에서는 정확히 "TSOM RCA → TSM 문제 관리"로 동일하게 작동합니다. TSOM이 "어디가 고장났는지"를 즉시 찾고, TSM의 문제 관리가 "왜 그렇게 고장났는지"를 사후에 파헤칩니다.

**리브랜딩 참고**

ServiceNow가 최근 TSM을 TPSM(Technology Provider Service Management)으로 리브랜딩하는 흐름이 있습니다. "통신사"에 국한하지 않고 "기술 제공자" 전체로 범위를 넓히려는 의도입니다. 하지만 실무에서는 여전히 TSM/TSOM으로 통용되고 있으니, 양쪽 명칭을 모두 알아두는 것이 좋습니다.

**출처**

- TSM Overview (ServiceNow Community): https://www.servicenow.com/community/telecom-articles/telecommunication-service-management-tsm-overview/ta-p/2765097
- TSM 공식 제품 페이지 (ServiceNow): https://www.servicenow.com/products/telecommunications-service-management.html
- TSOM 공식 제품 페이지 (ServiceNow): https://www.servicenow.com/products/telecommunications-service-operations.html

**변경 이력**

- 2026-04-13 — 최초 작성


**약어 정리 (누적)**

- **RCA** — Root Cause Analysis: 근본 원인 분석
- **MTTR** — Mean Time To Resolve: 평균 장애 해결 시간
- **KEDB** — Known Error Database: 알려진 오류 데이터베이스
- **RFC** — Request for Change: 변경 요청서
- **CI** — Configuration Item: 구성 항목
- **CMDB** — Configuration Management Database: 구성 관리 데이터베이스
- **SME** — Subject Matter Expert: 분야 전문가
- **FMEA** — Failure Mode and Effects Analysis: 고장 모드·영향 분석
- **TSM** — Telecommunications Service Management: ServiceNow 통신사 전용 서비스 관리
- **TSOM** — Telecommunications Service Operations Management: ServiceNow 통신사 전용 운영 관리
- **TPSM** — Technology Provider Service Management: TSM의 리브랜딩 명칭
- **CSP** — Communication Service Provider: 통신 서비스 제공자
- **CSM** — Customer Service Management: 고객 서비스 관리
- **FSM** — Field Service Management: 현장 서비스 관리
- **NOC** — Network Operations Center: 네트워크 운영 센터
- **TMF** — TM Forum: 통신 산업 표준화 기구
- **OSS/BSS** — Operations/Business Support System: 운영/비즈니스 지원 시스템


**시리즈 전체 목차**

- Part 1: 전체 개요 — ITSM, ITOM, ITAM 개념과 관계 (완료)
- Part 2: ITSM 상세 — 서비스 데스크, SLA, 인시던트/문제/변경 관리 (완료)
- Part 3: ITOM 상세 — 모니터링, 이벤트 관리, AIOps (완료)
- Part 4: ITAM 상세 — 자산 관리, 라이선스 최적화, 비용 절감 (완료)
- Part 5: ServiceNow 플랫폼 — ITIL 5, 통합 플랫폼, 도구 비교 (완료)
- Part 6: 거버넌스 체계 — COBIT, ISO/IEC 20000, 거버넌스 로드맵 (완료)
- Part 7: 통신사 레퍼런스 케이스 — BT, A1, Deutsche Telekom, Vodafone 사례 (완료)
- **Part 8: Q&A 모음 (이 글)** — 시리즈를 읽으며 받은 질문 누적 (지속 업데이트)

추가 질문이 있으면 댓글로 남겨주세요. 이 문서에 답변을 추가합니다.
