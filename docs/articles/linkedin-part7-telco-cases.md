# 통신사의 성공적인 ITSM 적용 사례 — BT, A1, Deutsche Telekom, Vodafone

> LinkedIn 시리즈 | Part 7 (보너스): 통신사 레퍼런스 케이스
> 작성일: 2026-04-09

---

Part 1~6에서 ITSM·ITOM·ITAM, ServiceNow, ITIL 5, 그리고 거버넌스 체계(COBIT·ISO 20000)까지 다뤘습니다. 이론과 프레임워크는 충분히 얘기한 셈인데, 시리즈를 공유하고 나서 이런 질문을 받았습니다.

> "좋은 내용인데, 실제로 통신사에서 성공한 사례가 있나요? 숫자가 있는 레퍼런스가 있으면 내부 설득이 훨씬 쉬울 것 같아요."

맞는 말입니다. 그래서 공식 소스로 검증 가능한 통신사 ITSM 성공 사례 네 곳을 정리했습니다. 특히 **BT Group**은 규모·접근법·공개된 지표 모두에서 교과서 같은 사례라 가장 먼저 다루겠습니다.

---

## 1. BT Group (영국) — "56개를 1개로" 통합 여정

BT는 Part 5에서 이야기한 **"도구가 쪼개져 있으면 벌어지는 일"**이 극단적으로 누적된 상태였습니다. 2022년 공식 발표된 수치를 보면 상황이 실감납니다.

### 시작점의 현실

- **56개의 레거시 서비스 관리 플랫폼** 공존
- **76가지의 서로 다른 서비스 프로세스 구현 방식**
- 부서마다 다른 도구, 다른 용어, 다른 이력 — 전형적인 파편화

이 상태에서 BT는 ServiceNow를 "단일 플랫폼"으로 정하고, 3단계 진화 로드맵을 공식화했습니다.

### 3단계 진화 모델 — Customer Ops → AI Ops → Zero Ops

BT의 접근이 특히 흥미로운 건, "한 번에 AI 운영까지 가겠다"가 아니라 **단계를 명확히 나눴다**는 점입니다.

1. **Customer Ops (1단계, 현재)** — 모든 서비스 관리 프로세스를 ServiceNow 하나로 통합. 기본 자동화와 셀프서비스 중심.
2. **AI Ops (2단계)** — 실시간 AI 인사이트를 워크플로우에 내재화. 선제적·예측적 경보 체계. Google Cloud 데이터 저장소와 결합해 AI가 운영 맥락을 이해하는 단계.
3. **Zero Ops (3단계)** — 자동화 계층이 자가 치유(self-healing) 운영을 수행. 사람이 개입하지 않아도 대부분의 문제가 감지·해결되는 상태.

이 순서가 중요합니다. **1단계 없이 2단계는 불가능**합니다. 데이터가 한곳에 모이지 않으면 AI가 학습할 재료가 없거든요. Part 3에서 다룬 AIOps와 Part 5의 통합 플랫폼이 왜 같은 얘기인지, BT 사례가 정확하게 보여줍니다.

### 초기 공개 지표

1단계 롤아웃 초기에 공개된 숫자가 이 정도입니다.

- **서비스 요청 처리 공수 50% 감소**
- **변경 배포 속도 20배 개선**
- **2027년까지 £25M(약 450억 원) 누적 절감** 목표

"변경 배포 속도 20배"는 특히 인상적입니다. Part 2에서 다룬 변경 관리가 "느려서 답답한 프로세스"가 아니라 "제대로 자동화하면 오히려 빨라지는 프로세스"라는 것을 보여주는 숫자입니다.

### BT 사례의 교훈

- **레거시 통합은 숫자로 말할 수 있다** — "56 → 1"이라는 수치만으로도 내부 설득이 됩니다.
- **AI는 2단계** — 통합 플랫폼과 데이터 기반이 먼저입니다.
- **단계별 로드맵이 현실적** — 2022년 발표, 2027년 완성 목표. 5년 계획으로 통신사 규모의 전환을 추진합니다.

---

## 2. A1 Telekom Austria — 예측 분석으로 자동 해결까지

오스트리아 최대 통신사 A1 Telekom은 조금 다른 각도에서 참고할 만합니다. **예측 분석(Predictive Analytics)** 활용이 특히 공개적으로 다뤄진 사례입니다.

### 배경

- 과거의 운영 비효율과 비용 문제 해결이 목표
- B2B 고객 경험 개선이 핵심 동기
- 2018년 ServiceNow 도입 결정

### 특징 — 티켓이 생기는 순간 AI가 해결책을 추천

A1의 접근에서 주목할 지점은 예측 분석의 실무 적용입니다.

- 사용자가 티켓을 생성하면, **AI가 과거 이력을 학습해 해결책 확률을 제시**
- 일부 케이스는 **이론적으로 자동 해결까지 수행**
- ITSM과 ITOM을 **단일 플랫폼**으로 통합해 데이터가 한 곳에 모이도록 설계
- 2020년부터는 BRIGHT 컨설팅과 협력해 프로세스 고도화

### A1 사례의 교훈

Part 2에서 다룬 내용을 다시 꺼내보면, 인시던트 관리를 "모든 작은 사건을 포착하는 체계"라고 했죠. A1의 예측 분석은 **"작은 인시던트도 다 기록했기 때문에 가능"**했던 것입니다. 데이터 없이는 AI도 없습니다. "크리티컬 이벤트만 관리하면 된다"는 접근으로는 이런 수준의 자동화에 도달할 수 없다는 것을 실증해 주는 사례입니다.

---

## 3. Deutsche Telekom — 장기 파트너십 + 주권 클라우드

독일 최대 통신사 Deutsche Telekom은 **규제 환경에서 ITSM을 어떻게 운영하느냐**의 관점에서 흥미롭습니다.

### 배경

- ServiceNow와 2014년부터 파트너십 유지 (약 12년)
- 전사 ITSM 시스템 전면 교체 진행 중
- 셀프서비스 포털 확대로 IT팀에 도달하는 인시던트 감축이 목표

### 차별화 포인트

Deutsche Telekom의 접근에서 두 가지가 돋보입니다.

- **Sovereign Partner Cloud** — ServiceNow의 주권 클라우드 제공자로 협력을 확장했습니다. 독일·EU의 규제 산업(금융, 공공, 의료) 고객이 데이터 주권을 유지하면서 ServiceNow를 사용할 수 있도록 하는 구조입니다.
- **Low-code로 시민 개발자 육성** — 현업이 직접 워크플로우를 만들 수 있도록 Now Platform의 로우코드 기능을 확장. IT팀이 모든 요구사항을 받아서 처리하는 게 아니라, 현업에 권한을 일부 위임하는 방향입니다.

### Deutsche Telekom 사례의 교훈

Part 6에서 다룬 거버넌스 관점과 직접 연결됩니다. **강한 규제(COBIT MEA03: 외부 요구사항 준수)** 아래에서도 효율화를 포기하지 않는 방식을 보여줍니다. 통신사처럼 전기통신사업법·개인정보보호법·금융 규제가 겹치는 환경에서 참고할 만합니다.

---

## 4. Vodafone — 디지털 전환의 일부로서 ITSM

Vodafone은 공식 커스터머 스토리로 여러 차례 언급된 글로벌 통신 그룹입니다. 구체적 지표는 공개 자료에 많지 않지만, 방향성은 명확합니다.

- ServiceNow를 **디지털 전환의 핵심 도구**로 활용
- "고객이 원하는 채널로, 원하는 시간에(channel of choice)" 서비스한다는 목표
- 고객 접점의 통합이 ITSM·ITOM 통합과 자연스럽게 연결되는 구조

구체적 수치가 공개된 다른 사례에 비해 참고 가치는 조금 덜하지만, **"ITSM을 단독 프로젝트가 아니라 디지털 전환의 한 축으로 본다"**는 관점 자체가 시사점입니다. Part 1에서 "ITSM·ITOM·ITAM이 연결돼야 한다"고 했던 이야기의 한 단계 위 버전이죠.

---

## 국내 통신사 사례는 왜 안 보이나

솔직하게 말씀드리면, SK텔레콤·KT·LG유플러스의 **구체적인 ITSM 성과 지표**는 영문·국문 공개 자료에서 특정하기 어려웠습니다. 제가 확인한 수준은 이렇습니다.

- **SK텔레콤**: SK C&C가 운영하는 ITSM 체계를 사용하는 고객사 중 하나라는 언급이 있습니다. SK C&C가 캐나다 Telus International과 제휴해 ITSM 체계를 초기 도입한 기록은 있지만, 오래된 기사 기반이라 현재 상태는 직접 확인이 필요합니다.
- **KT, LG유플러스**: 개별 통신사의 ServiceNow 또는 ITSM 상세 사례는 공개 자료에서 찾기 어려웠습니다.

국내 사례가 필요하시다면 다음 경로를 권장합니다.

- ServiceNow Korea의 고객 세미나 자료
- SK C&C, LG CNS, 포스코DX 등 국내 구축 파트너사의 케이스 스터디
- Gartner Peer Insights의 한국 리뷰
- 각사 IR 자료와 기술 블로그

국내 통신사들도 ITSM을 쓰지 않을 리 없지만, **대외 공개를 안 할 뿐**이라는 것이 현실적인 관측입니다. 이 점에서 BT처럼 로드맵을 공식 발표한 사례는 예외에 가깝습니다.

---

## 네 사례에서 뽑은 공통 패턴

시리즈 Part 2~6의 관점에서 이 사례들을 보면 공통점이 뚜렷합니다.

- **레거시 통합부터 시작** — BT의 56개 통합이 대표적. 데이터와 프로세스를 한곳에 모으는 게 1단계
- **CMDB가 모든 것의 전제** — 단일 데이터 모델 없이는 AI도, 자동화도, 분석도 불가능
- **AIOps·예측 분석은 2단계** — A1의 예측 분석, BT의 AI Ops 단계 모두 "데이터가 쌓인 후"의 이야기
- **규제·경험·비용을 동시에** — Deutsche Telekom의 주권 클라우드, Vodafone의 고객 채널 통합
- **단계별 로드맵** — "한 번에 완성"은 없음. BT는 5년, A1은 2018년 시작 후 수년간 고도화
- **수치로 측정** — 절감액, 공수 감소율, 속도 개선 등 정량 지표로 성과를 증명

특히 BT의 **"50% 공수 감소 + 20배 변경 속도 + £25M 절감"**은 시리즈에서 강조한 통합 플랫폼 전략의 가치를 숫자로 가장 명확하게 보여줍니다. 내부에서 "왜 통합해야 하나"를 설득할 때 인용하기 좋은 케이스입니다.

---

## 실무적 팁 — 이 사례들을 어떻게 활용할까

단순히 "BT가 했으니 우리도 하자"가 아니라, 이 사례들을 내부 설득과 로드맵 수립의 재료로 쓰는 방법입니다.

1. **현 상태 진단** — 우리 조직에는 몇 개의 서비스 관리 도구가 있나? (BT의 56개를 기준선으로 삼아보세요)
2. **단계 분리** — 통합 → AI → Zero-touch의 3단계 중 우리는 어디인가? 대부분 조직은 1단계에 있습니다.
3. **지표 설정** — "무엇을 몇 %까지 개선할 것인가"를 BT·A1의 숫자를 참고해 설정
4. **5년 로드맵** — 통신사 규모에서는 1~2년으로 끝나지 않는다는 것을 기대치로 설정

이 네 가지가 준비되면, Part 6의 거버넌스 로드맵(ITIL → COBIT → ISO 20000)과 결합해 기술·프로세스·거버넌스 세 축의 균형 잡힌 계획을 세울 수 있습니다.

---

## 시리즈를 (이번엔 진짜로) 마무리하며

Part 1에서 레스토랑 비유로 시작해서, Part 7의 실제 레퍼런스 사례까지 왔습니다. 시리즈 전체를 한 문장으로 압축하면 이렇습니다.

> **ITSM·ITOM·ITAM을 따로 떼어 보지 말고, 프로세스·거버넌스·플랫폼의 세 축으로 연결해서 단계적으로 키워라. 그리고 그 과정을 숫자로 측정해라.**

BT의 "56 → 1" 통합이든, A1의 예측 분석이든, Deutsche Telekom의 주권 클라우드든 — 전부 같은 원칙에서 출발합니다. 규모와 순서만 다를 뿐이죠.

이 시리즈가 여러분 조직의 IT 운영·거버넌스 여정에 조금이라도 도움이 됐다면 기쁘겠습니다. 국내 통신사 사례나 본인의 경험을 댓글로 공유해 주시면 시리즈의 다음 업데이트에 반영하겠습니다.

긴 시리즈 끝까지 읽어주셔서 감사합니다.

---

## 약어 정리

| 약어 | 풀네임 | 한 마디로 |
|------|--------|-----------|
| **Zero Ops** | Zero-touch Operations | 사람 개입 없이 운영되는 상태 |
| **AIOps** | AI for IT Operations | AI/ML 기반 IT 운영 자동화 |
| **Sovereign Cloud** | - | 데이터 주권이 보장된 클라우드 |
| **Low-code** | - | 최소 코딩으로 앱·워크플로우를 만드는 방식 |
| **Predictive Analytics** | - | 과거 데이터로 미래 결과를 예측하는 기법 |
| **B2B** | Business to Business | 기업 간 거래 |
| **CSP** | Communication Service Provider | 통신 서비스 제공자 |

---

## 출처

- [BT aims for £25m in savings by leaping towards AI-led operations with ServiceNow (BT Newsroom)](https://newsroom.bt.com/bt-aims-for-25m-in-savings-by-leaping-towards-ai-led-operations-with-servicenow/)
- [BT sees $30m+ savings in five years with ServiceNow project (The Register)](https://www.theregister.com/2022/05/11/bt_servicenow/)
- [BT bets big on AI with ServiceNow to cut legacy baggage (The Register, 2024)](https://www.theregister.com/2024/07/03/bt_servicenow_savings/)
- [A1 Telekom — ServiceNow Customer Story](https://www.servicenow.com/customers/a1-telekom.html)
- [A1 Streamlines ITSM and ITOM Processes on ServiceNow (BRIGHT)](https://bright.consulting/casestudies/a1-telekom-servicenow-itsm-and-itom-processes/)
- [Deutsche Telekom — ServiceNow Customer Story](https://www.servicenow.com/customers/deutsche-telekom.html)
- [Vodafone — ServiceNow Customer Story](https://www.servicenow.com/customers/vodafone.html)
- [Telefonica Tech UK selects ServiceNow ITSM (Apps Run The World)](https://www.appsruntheworld.com/customers-database/purchases/view/telefonica-tech-uk-united-kingdom-selects-servicenow-itsm-for-it-service-management)

---

#ITSM #ITIL #ServiceNow #통신 #디지털전환 #AIOps #BTGroup #DeutscheTelekom #A1Telekom #Vodafone #사례연구
