ITSM/ITOM/ITAM 시리즈 Part 7 (보너스) — 통신사의 성공적인 ITSM 적용 사례

Part 1~6에서 ITSM·ITOM·ITAM, ServiceNow, ITIL 5, 거버넌스 체계(COBIT·ISO 20000)까지 이론과 프레임워크를 다뤘습니다. 시리즈 이후 가장 많이 받은 질문 중 하나가 "실제로 통신사에서 성공한 사례가 있나요? 숫자가 있는 레퍼런스가 있으면 내부 설득이 훨씬 쉬울 것 같아요"였습니다.

이번 Part 7에서는 공식 소스로 검증 가능한 네 곳의 글로벌 통신사 사례를 정리합니다. 특히 **BT Group**은 규모·접근법·공개된 지표 모두에서 교과서 같은 사례입니다.


**사례 요약 — 한눈에 보기**

- **BT Group (영국)** — 대형 통신사. 레거시 56개 → 단일 플랫폼 통합, 3단계 진화 모델. 공개 지표: 공수 50% 감소, 변경 속도 20배, £25M 절감 목표.
- **A1 Telekom Austria (오스트리아)** — 오스트리아 최대 통신사. 예측 분석으로 티켓 자동 해결 시도. 구체 수치는 미공개, B2B 고객 경험 개선이 목표.
- **Deutsche Telekom (독일)** — 유럽 최대급 통신사. 주권 클라우드 + Low-code 거버넌스. ServiceNow와 2014년부터 파트너십.
- **Vodafone (영국·글로벌)** — 글로벌 통신 그룹. 디지털 전환의 핵심 도구로 ServiceNow 활용. 구체 수치는 미공개, 고객 채널 통합이 목표.


**BT Group — "56 → 1" 통합 여정**

BT Group은 공개된 통신사 ITSM 전환 사례 중 가장 상세한 수치가 공개된 케이스입니다. Part 5에서 다룬 "도구가 쪼개져 있으면 벌어지는 일"의 극단적 사례이자, 통합 플랫폼 전략의 가치를 숫자로 증명한 사례이기도 합니다.

**전환 전 상태**

BT가 2022년 공식 발표한 시점의 파편화 수준은 놀랍습니다.

- **레거시 서비스 관리 플랫폼 56개** — 각 부서·영역마다 별도 도구를 운영하고 있었습니다.
- **서비스 프로세스 구현 방식 76가지** — 같은 "변경 관리"도 부서마다 다르게 구현되고 있었습니다.
- **통합 데이터 모델 부재** — CMDB 같은 단일 진실의 원천이 없었습니다.

이는 통신사 규모의 조직에서 자연스럽게 발생하는 파편화입니다. 인수·합병, 사업부 독립 운영, 시대별 도입 기술의 차이가 누적된 결과입니다.

**3단계 진화 모델 — Customer Ops → AI Ops → Zero Ops**

BT의 접근이 특히 흥미로운 건, "한 번에 AI 운영까지 가겠다"가 아니라 단계를 명확히 나눴다는 점입니다.

- **1단계 Customer Ops (현재)** — 모든 서비스 관리 프로세스를 ServiceNow 하나로 통합하고, 기본 자동화와 셀프서비스를 구축하는 단계입니다. 단일 플랫폼과 CMDB 통합이 전제입니다.
- **2단계 AI Ops** — 실시간 AI 인사이트를 워크플로우에 내재화하고, 선제적·예측적 경보 체계를 구축하는 단계입니다. 1단계에서 축적된 데이터와 Google Cloud 데이터 저장소가 전제입니다.
- **3단계 Zero Ops** — 자가 치유(self-healing) 운영을 수행하는 단계입니다. 사람이 개입하지 않아도 대부분의 문제가 감지·해결되는 상태입니다. 1·2단계 완성과 자동화 계층 성숙이 전제입니다.

이 모델의 핵심 메시지는 "데이터 없이는 AI 없다"입니다. 1단계에서 모든 이벤트·인시던트·변경·요청이 하나의 플랫폼에 축적돼야, 2단계에서 AI가 학습할 재료가 생깁니다. Part 3에서 다룬 AIOps와 Part 5의 통합 플랫폼이 왜 같은 얘기인지, BT 사례가 정확하게 보여줍니다.

**초기 공개 지표 (2022년 시점)**

1단계 롤아웃 초기에 공개된 숫자가 이 정도입니다.

- **서비스 요청 처리 공수 50% 감소** — 자동화와 셀프서비스의 효과입니다.
- **변경 배포 속도 20배 개선** — 통합 워크플로우와 표준화의 효과입니다.
- **2027년까지 £25M(약 450억 원) 누적 절감 목표** — 5년 계획의 재무 목표입니다.

"변경 배포 속도 20배"는 특히 인상적입니다. Part 2에서 다룬 변경 관리가 "느려서 답답한 프로세스"가 아니라 "제대로 자동화하면 오히려 빨라지는 프로세스"라는 것을 보여주는 숫자입니다.

**기술 통합 구조**

ServiceNow는 BT의 Google Cloud 데이터 저장소와 통합되어 있습니다. ServiceNow 플랫폼이 ITSM·ITOM·ITAM 워크플로우 통합 허브 역할을 하고, Google Cloud가 대규모 운영 데이터 저장·분석 기반을 제공하며, 그 위에서 AI/ML 모델이 예측·탐지·근본 원인 분석을 수행합니다. 자동화 워크플로우 엔진이 실행 계층을 담당합니다.

**BT 사례의 교훈**

- **레거시 통합은 숫자로 말할 수 있다** — "56 → 1"이라는 수치만으로도 내부 설득이 됩니다.
- **AI는 2단계** — 통합 플랫폼과 데이터 기반이 먼저입니다.
- **단계별 로드맵이 현실적** — 2022년 발표, 2027년 완성 목표. 5년 계획으로 통신사 규모의 전환을 추진합니다.
- **변경 관리가 속도의 레버가 될 수 있다** — 제대로 자동화된 변경 관리는 오히려 배포 속도를 높입니다.


**A1 Telekom Austria — 예측 분석 기반 자동 해결**

오스트리아 최대 통신사 A1 Telekom은 조금 다른 각도에서 참고할 만합니다. 예측 분석 활용이 특히 공개적으로 다뤄진 사례입니다.

**배경**

- 오스트리아 최대 통신사입니다.
- 2018년 ServiceNow를 도입했습니다.
- 과거의 운영 비효율과 비용 문제 해결이 목표였습니다.
- B2B 고객 경험 개선이 핵심 동기였습니다.
- Thomas Eder(Head of ITSM Tools)가 전사 롤아웃을 담당했습니다.

**차별화 포인트 — 티켓 생성 순간 AI가 해결책을 추천**

A1의 특징은 ITSM 통합과 예측 분석을 조기에 결합한 것입니다.

- **티켓 생성 시 해결책 추천** — 사용자가 티켓을 올리면 AI가 과거 이력 기반으로 해결책 확률을 제시합니다.
- **자동 해결 후보 식별** — 높은 확률로 특정 패턴에 해당하는 티켓은 이론적으로 자동 해결까지 수행합니다.
- **ITSM + ITOM 단일 플랫폼** — 데이터가 한곳에 모이도록 플랫폼을 통합했습니다.
- **파트너 협력 고도화** — 2020년부터 BRIGHT 컨설팅과 협력해 프로세스를 고도화했습니다.

**A1 사례의 교훈**

Part 2에서 "인시던트 관리는 IT 운영의 최소 측정 단위이며, 모든 작은 사건을 포착해야 한다"고 했던 이야기가 A1 사례에서 실증됩니다. 작은 인시던트까지 모두 기록했기 때문에 예측 분석이 가능했고, 예측 분석이 있기 때문에 자동 해결이 가능합니다. 이는 "크리티컬 이벤트만 관리하면 된다"는 축소 전략으로는 도달할 수 없는 수준의 자동화를 보여줍니다.


**Deutsche Telekom — 주권 클라우드와 거버넌스**

독일 최대 통신사 Deutsche Telekom은 규제 환경에서 ITSM을 어떻게 운영하느냐의 관점에서 흥미롭습니다.

**배경**

- 유럽 최대급 통신사입니다.
- ServiceNow와 2014년부터 파트너십을 유지해 왔습니다(약 12년).
- 현재 전사 ITSM 시스템 전면 교체를 진행 중이며, 셀프서비스 포털 확대로 IT팀에 도달하는 인시던트 감축이 목표입니다.

**차별화 포인트 1: Sovereign Partner Cloud (주권 클라우드)**

Deutsche Telekom은 ServiceNow의 주권 파트너 클라우드 제공자로 협력을 확장했습니다.

- **목적** — 독일·EU의 규제 산업(금융, 공공, 의료) 고객이 데이터 주권을 유지하면서 ServiceNow를 사용할 수 있도록 합니다.
- **가치** — 국내·EU 데이터 보호법 준수와 글로벌 ITSM 플랫폼의 혜택을 동시에 누릴 수 있습니다.
- **의미** — 규제가 강한 조직도 "클라우드 ITSM"을 선택할 수 있는 길이 열립니다.

**차별화 포인트 2: Low-code 기반 시민 개발자(Citizen Developer)**

Deutsche Telekom은 Now Platform의 로우코드 기능을 확장해 현업이 직접 워크플로우를 만들 수 있도록 하고 있습니다.

- IT팀이 모든 요구사항을 받아서 처리하는 병목을 해소합니다.
- 플랫폼 내부에 승인·감사·정책이 내재돼 리스크를 제한합니다.
- AI로 비정형 데이터를 구조화하면서도 규제 요구사항을 충족합니다.

**Deutsche Telekom 사례의 교훈**

이 사례는 Part 6의 거버넌스 관점과 직접 연결됩니다. COBIT MEA03(외부 요구사항 준수 모니터링)과 APO13(보안 관리)이 기술적으로 뒷받침되는 구조이고, ITIL 5의 임베디드 거버넌스가 로우코드 워크플로우에 내재된 사례이기도 합니다. 통신사처럼 전기통신사업법, 개인정보보호법, 금융 규제가 겹치는 환경에서 "규제와 효율화를 동시에" 달성하는 방식의 레퍼런스로 활용할 수 있습니다.


**Vodafone — 디지털 전환의 핵심 도구로**

Vodafone은 공식 커스터머 스토리로 여러 차례 언급된 글로벌 통신 그룹입니다. 구체적 지표는 공개 자료에 많지 않지만, 방향성은 명확합니다.

- ServiceNow를 디지털 전환의 핵심 도구로 활용하고 있습니다.
- "고객이 원하는 채널로, 원하는 시간에(channel of choice)" 서비스한다는 목표를 가지고 있습니다.
- 고객 접점의 통합이 ITSM·ITOM 통합과 자연스럽게 연결되는 구조입니다.

구체적 수치가 공개된 다른 사례에 비해 참고 가치는 조금 덜하지만, "ITSM을 단독 프로젝트가 아니라 디지털 전환의 한 축으로 본다"는 관점 자체가 시사점입니다. Part 1에서 "ITSM·ITOM·ITAM이 연결돼야 한다"고 했던 이야기의 한 단계 위 버전이죠.


**국내 통신사 사례는 왜 안 보이나**

솔직하게 말씀드리면, SK텔레콤·KT·LG유플러스의 구체적인 ITSM 성과 지표는 영문·국문 공개 자료에서 특정하기 어려웠습니다. 제가 확인한 수준은 이렇습니다.

- **SK텔레콤** — SK C&C가 운영하는 ITSM 체계를 사용하는 고객사 중 하나라는 언급이 있습니다. SK C&C가 캐나다 Telus International과 제휴해 ITSM 체계를 초기 도입한 기록은 있지만, 오래된 기사 기반이라 현재 상태는 직접 확인이 필요합니다.
- **KT, LG유플러스** — 개별 통신사의 ServiceNow 또는 ITSM 상세 사례는 공개 자료에서 찾기 어려웠습니다.

국내 사례가 필요하시다면 다음 경로를 권장합니다.

- ServiceNow Korea의 고객 세미나 자료
- SK C&C, LG CNS, 포스코DX 등 국내 구축 파트너사의 케이스 스터디
- Gartner Peer Insights의 한국 리뷰
- 각사 IR 자료와 기술 블로그

국내 통신사들도 ITSM을 쓰지 않을 리 없지만, 대외 공개를 적극 하지 않는 경향이 있습니다. 이 점에서 BT처럼 로드맵을 공식 발표한 사례는 예외에 가깝습니다.


**네 사례에서 뽑은 공통 패턴**

시리즈 Part 2~6의 관점에서 이 사례들을 보면 공통점이 뚜렷합니다.

- **레거시 통합부터 시작** — BT의 56개 통합이 대표적입니다. 데이터와 프로세스를 한곳에 모으는 게 1단계입니다.
- **CMDB가 모든 것의 전제** — 단일 데이터 모델 없이는 AI도, 자동화도, 분석도 불가능합니다.
- **AIOps·예측 분석은 2단계** — A1의 예측 분석, BT의 AI Ops 단계 모두 "데이터가 쌓인 후"의 이야기입니다.
- **규제·경험·비용을 동시에** — Deutsche Telekom의 주권 클라우드, Vodafone의 고객 채널 통합이 대표적입니다.
- **단계별 로드맵** — "한 번에 완성"은 없습니다. BT는 5년, A1은 2018년 시작 후 수년간 고도화했습니다.
- **수치로 측정** — 절감액, 공수 감소율, 속도 개선 등 정량 지표로 성과를 증명합니다.

특히 BT의 "50% 공수 감소 + 20배 변경 속도 + £25M 절감"은 시리즈에서 강조한 통합 플랫폼 전략의 가치를 숫자로 가장 명확하게 보여줍니다. 내부에서 "왜 통합해야 하나"를 설득할 때 인용하기 좋은 케이스입니다.


**실무적 팁 — 이 사례들을 어떻게 활용할까**

단순히 "BT가 했으니 우리도 하자"가 아니라, 이 사례들을 내부 설득과 로드맵 수립의 재료로 쓰는 방법입니다.

- **1단계 현 상태 진단** — 우리 조직에는 몇 개의 서비스 관리 도구가 있나? BT의 56개를 기준선으로 삼아보세요.
- **2단계 단계 분리** — 통합 → AI → Zero-touch의 3단계 중 우리는 어디인가? 대부분 조직은 1단계에 있습니다.
- **3단계 지표 설정** — "무엇을 몇 %까지 개선할 것인가"를 BT·A1의 숫자를 참고해 설정합니다.
- **4단계 5년 로드맵** — 통신사 규모에서는 1~2년으로 끝나지 않는다는 것을 기대치로 설정합니다.

이 네 가지가 준비되면, Part 6의 거버넌스 로드맵(ITIL → COBIT → ISO 20000)과 결합해 기술·프로세스·거버넌스 세 축의 균형 잡힌 계획을 세울 수 있습니다.

**내부 설득용 핵심 수치 (BT 사례 기준)**

다음 수치들은 내부 경영진·이사회 설득 자료에 활용할 수 있는 검증된 레퍼런스입니다.

- **"56 → 1 플랫폼 통합"** — 레거시 통합의 가치 설명에 활용
- **"변경 배포 속도 20배 개선"** — 변경 관리 자동화의 효과 설명에 활용
- **"서비스 요청 공수 50% 감소"** — 운영 효율 개선 근거로 활용
- **"£25M 5년 절감 목표"** — 재무적 타당성 설명에 활용

이 수치들은 모두 BT의 2022년 공식 발표와 이후 후속 보도를 통해 검증된 내용입니다.


**시리즈를 (이번엔 진짜로) 마무리하며**

Part 1에서 레스토랑 비유로 시작해서, Part 7의 실제 레퍼런스 사례까지 왔습니다. 시리즈 전체를 한 문장으로 압축하면 이렇습니다.

**ITSM·ITOM·ITAM을 따로 떼어 보지 말고, 프로세스·거버넌스·플랫폼의 세 축으로 연결해서 단계적으로 키워라. 그리고 그 과정을 숫자로 측정해라.**

BT의 "56 → 1" 통합이든, A1의 예측 분석이든, Deutsche Telekom의 주권 클라우드든, Vodafone의 고객 채널 통합이든 — 전부 같은 원칙에서 출발합니다. 규모와 순서만 다를 뿐이죠.

이 시리즈가 여러분 조직의 IT 운영·거버넌스 여정에 조금이라도 도움이 됐다면 기쁘겠습니다. 국내 통신사 사례나 본인의 경험을 댓글로 공유해 주시면 시리즈의 다음 업데이트에 반영하겠습니다.

긴 시리즈 끝까지 읽어주셔서 감사합니다.


**약어 정리**

- **Zero Ops** — Zero-touch Operations: 사람 개입 없이 운영되는 상태
- **AIOps** — AI for IT Operations: AI/ML 기반 IT 운영 자동화
- **Predictive Analytics** — 과거 데이터 기반 미래 예측 기법
- **Sovereign Cloud** — 데이터 주권이 보장된 클라우드
- **Low-code** — 최소 코딩으로 앱·워크플로우 개발 방식
- **CSP** — Communication Service Provider: 통신 서비스 제공자
- **B2B** — Business to Business: 기업 간 거래
- **KPI** — Key Performance Indicator: 핵심 성과 지표


**시리즈 전체 목차**

- Part 1: 전체 개요 — ITSM, ITOM, ITAM 개념과 관계 (완료)
- Part 2: ITSM 상세 — 서비스 데스크, SLA, 인시던트/문제/변경 관리 (완료)
- Part 3: ITOM 상세 — 모니터링, 이벤트 관리, AIOps (완료)
- Part 4: ITAM 상세 — 자산 관리, 라이선스 최적화, 비용 절감 (완료)
- Part 5: ServiceNow 플랫폼 — ITIL 5, 통합 플랫폼, 도구 비교 (완료)
- Part 6: 거버넌스 체계 — COBIT, ISO/IEC 20000, 거버넌스 로드맵 (완료)
- **Part 7: 통신사 레퍼런스 케이스 (이 글)** — BT, A1 Telekom, Deutsche Telekom, Vodafone 사례 분석 (완료)


**출처**

본 글의 모든 수치와 사례 내용은 다음 공식 소스에서 검증되었습니다.

- BT aims for £25m in savings by leaping towards AI-led operations with ServiceNow (BT Newsroom): https://newsroom.bt.com/bt-aims-for-25m-in-savings-by-leaping-towards-ai-led-operations-with-servicenow/
- BT sees $30m+ savings in five years with ServiceNow project (The Register, 2022): https://www.theregister.com/2022/05/11/bt_servicenow/
- BT bets big on AI with ServiceNow to cut legacy baggage (The Register, 2024): https://www.theregister.com/2024/07/03/bt_servicenow_savings/
- BT aims for £25 million in savings with ServiceNow (Intelligent CIO Europe): https://www.intelligentcio.com/eu/2022/05/12/bt-aims-for-25-million-in-savings-by-leaping-towards-ai-led-operations-with-servicenow/
- A1 Telekom — ServiceNow Customer Story: https://www.servicenow.com/customers/a1-telekom.html
- A1 Streamlines ITSM and ITOM Processes on ServiceNow (BRIGHT): https://bright.consulting/casestudies/a1-telekom-servicenow-itsm-and-itom-processes/
- Telekom Austria Group Empowers its $4B Business with Cloud-Enabled Digital Service Management (BRIGHT): https://bright.consulting/casestudies/cloud-enabled-digital-service-management-servicenow-a1-austria/
- Deutsche Telekom — ServiceNow Customer Story: https://www.servicenow.com/customers/deutsche-telekom.html
- Vodafone — ServiceNow Customer Story: https://www.servicenow.com/customers/vodafone.html
- Telefonica Tech UK selects ServiceNow ITSM (Apps Run The World): https://www.appsruntheworld.com/customers-database/purchases/view/telefonica-tech-uk-united-kingdom-selects-servicenow-itsm-for-it-service-management

궁금한 점이나 국내 사례 공유가 있으면 댓글로 남겨주세요.
