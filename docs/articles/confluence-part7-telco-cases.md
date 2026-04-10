# 통신사의 성공적인 ITSM 적용 사례 — 글로벌 레퍼런스 분석

| 항목 | 내용 |
|------|------|
| **작성자** | ymlee |
| **작성일** | 2026-04-09 |
| **대상 독자** | 전사 임직원 (IT 운영, 거버넌스, 전략, 경영진) |
| **시리즈** | IT 서비스 관리 이해하기 Part 7 (보너스: 통신사 레퍼런스 케이스) |
| **라벨** | `itsm` `servicenow` `telco` `case-study` `bt` `a1telekom` `deutschetelekom` `vodafone` |

---

## 이 글의 목적

Part 1~6에서 ITSM·ITOM·ITAM, ServiceNow, ITIL 5, 거버넌스 체계까지 이론과 프레임워크를 다뤘습니다. 이번 Part 7은 **실제 통신사에서 ITSM이 어떻게 성공적으로 적용됐는지**를 공식 소스로 검증 가능한 네 가지 사례를 통해 정리합니다. 내부 설득 자료, 로드맵 수립, 벤치마킹의 기초 자료로 활용할 수 있습니다.

> **주의**: 본 글에 인용된 수치는 2022~2024년 사이 공식 발표된 자료를 기준으로 합니다. 국내 통신사의 구체적 지표는 공개 자료가 제한적이어서, 글로벌 사례 중심으로 분석합니다.

---

## 1. 사례 요약 — 한눈에 보기

| 사례 | 국가 | 규모 | 핵심 특징 | 공개 지표 |
|------|------|------|---------|---------|
| **BT Group** | 영국 | 대형 통신사 | 레거시 56개 → 단일 플랫폼, 3단계 진화 모델 | 공수 50% 감소, 변경 속도 20배, £25M 절감 목표 |
| **A1 Telekom Austria** | 오스트리아 | 오스트리아 최대 통신사 | 예측 분석으로 티켓 자동 해결 시도 | 구체 수치 미공개, B2B 고객 경험 개선 |
| **Deutsche Telekom** | 독일 | 유럽 최대급 통신사 | 주권 클라우드 + Low-code 거버넌스 | ServiceNow 2014년부터 파트너십 |
| **Vodafone** | 영국·글로벌 | 글로벌 통신 그룹 | 디지털 전환의 핵심 도구로 활용 | 구체 수치 미공개, 고객 채널 통합 |

---

## 2. BT Group — "56 → 1" 통합 여정

BT Group은 공개된 통신사 ITSM 전환 사례 중 **가장 상세한 수치가 공개된 케이스**입니다. Part 5에서 다룬 "도구가 쪼개져 있으면 벌어지는 일"의 극단적 사례이자, 통합 플랫폼 전략의 가치를 숫자로 증명한 사례이기도 합니다.

### 2.1 전환 전 상태

BT가 2022년 공식 발표한 시점의 파편화 수준은 다음과 같습니다.

| 항목 | 수치 | 의미 |
|------|------|------|
| **레거시 서비스 관리 플랫폼** | 56개 | 각 부서·영역마다 별도 도구 |
| **서비스 프로세스 구현 방식** | 76가지 | 같은 "변경 관리"도 부서마다 다르게 구현 |
| **통합 데이터 모델** | 없음 | CMDB 단일 진실의 원천 부재 |

이는 통신사 규모의 조직에서 자연스럽게 발생하는 파편화입니다. 인수·합병, 사업부 독립 운영, 시대별 도입 기술의 차이가 누적된 결과입니다.

### 2.2 접근 전략 — 3단계 진화 모델

BT는 "한 번에 AI 운영까지"가 아니라 명확한 3단계 로드맵을 발표했습니다.

| 단계 | 명칭 | 핵심 활동 | 기술적 전제 |
|------|------|---------|----------|
| **1단계** | Customer Ops | 모든 서비스 관리 프로세스를 ServiceNow 하나로 통합, 기본 자동화와 셀프서비스 | 단일 플랫폼, CMDB 통합 |
| **2단계** | AI Ops | 실시간 AI 인사이트 내재화, 선제적·예측적 경보 | 1단계 데이터 축적 + Google Cloud 데이터 저장소 |
| **3단계** | Zero Ops | 자가 치유(Self-healing) 운영, 사람 개입 최소화 | 1·2단계 완성, 자동화 계층 성숙 |

이 모델의 핵심 메시지는 **"데이터 없이는 AI 없다"**입니다. 1단계에서 모든 이벤트·인시던트·변경·요청이 하나의 플랫폼에 축적돼야, 2단계에서 AI가 학습할 재료가 생깁니다.

### 2.3 초기 공개 지표 (2022년 시점)

1단계 롤아웃 초기에 BT가 공개한 성과 지표입니다.

| 지표 | 개선율 | 의미 |
|------|------|------|
| 서비스 요청 처리 공수 | **50% 감소** | 자동화와 셀프서비스의 효과 |
| 변경 배포 속도 | **20배 개선** | 통합 워크플로우 + 표준화의 효과 |
| 2027년까지 누적 절감 목표 | **£25M (약 450억 원)** | 5년 계획의 재무 목표 |

"변경 배포 속도 20배"는 특히 의미가 큽니다. Part 2에서 변경 관리가 "리스크 관리를 위해 필요한 통제"라고 했는데, BT 사례는 **제대로 통합·자동화하면 변경 관리가 속도를 높이는 레버가 된다**는 것을 보여줍니다.

### 2.4 기술 통합 구조

ServiceNow는 BT의 **Google Cloud 데이터 저장소**와 통합되어 있습니다. 이는 Part 3에서 다룬 AIOps의 전형적인 패턴입니다.

| 레이어 | 역할 |
|--------|------|
| ServiceNow Platform | ITSM·ITOM·ITAM 워크플로우 통합 허브 |
| Google Cloud Data Repository | 대규모 운영 데이터 저장·분석 기반 |
| AI/ML 모델 | 예측·탐지·근본 원인 분석 |
| Workflow Engine | 자동화 실행 계층 |

### 2.5 BT 사례의 시사점

| 시사점 | 시리즈 연결 |
|--------|-----------|
| 레거시 통합은 수치로 말할 수 있다 | Part 5 "도구 파편화의 비용" |
| AI는 2단계, 통합이 1단계 | Part 3 AIOps + Part 5 CMDB 허브 |
| 5년 로드맵이 현실적이다 | Part 6 "작게 시작해서 성숙도를 높인다" |
| 변경 관리가 속도의 레버가 될 수 있다 | Part 2 변경 관리 |

---

## 3. A1 Telekom Austria — 예측 분석 기반 자동 해결

### 3.1 배경

| 항목 | 내용 |
|------|------|
| **규모** | 오스트리아 최대 통신사 |
| **도입 시점** | 2018년 ServiceNow 선정 |
| **주요 동기** | 운영 비효율·비용 해결, B2B 고객 경험 개선 |
| **담당자** | Thomas Eder (Head of ITSM Tools) |

### 3.2 차별화 포인트 — 예측 분석의 실무 적용

A1의 특징은 ITSM 통합과 **예측 분석(Predictive Analytics)**을 조기에 결합한 것입니다.

| 기능 | 설명 |
|------|------|
| **티켓 생성 시 해결책 추천** | 사용자가 티켓을 올리면 AI가 과거 이력 기반으로 해결책 확률을 제시 |
| **자동 해결 후보 식별** | 높은 확률로 특정 패턴에 해당하는 티켓은 이론적으로 자동 해결 가능 |
| **ITSM + ITOM 단일 플랫폼** | 데이터가 한곳에 모이도록 플랫폼 통합 |
| **파트너 협력 고도화** | 2020년부터 BRIGHT 컨설팅과 프로세스 고도화 |

### 3.3 A1 사례의 시사점

Part 2에서 "인시던트 관리는 IT 운영의 최소 측정 단위이며, 모든 작은 사건을 포착해야 한다"고 했던 이야기가 A1 사례에서 실증됩니다. **작은 인시던트까지 모두 기록했기 때문에 예측 분석이 가능**했고, 예측 분석이 있기 때문에 자동 해결이 가능합니다.

이는 "크리티컬 이벤트만 관리하면 된다"는 축소 전략으로는 도달할 수 없는 수준의 자동화를 보여줍니다. Part 2의 "인시던트 관리 vs 크리티컬 이벤트 관리" 논의의 실증 사례로 활용할 수 있습니다.

---

## 4. Deutsche Telekom — 주권 클라우드와 거버넌스

### 4.1 배경

| 항목 | 내용 |
|------|------|
| **규모** | 유럽 최대급 통신사 |
| **파트너십 시작** | 2014년 ServiceNow와 협력 개시 (약 12년) |
| **현재 목표** | 전사 ITSM 시스템 전면 교체, 셀프서비스 확대 |

### 4.2 차별화 포인트 — 규제 환경에서의 ITSM 운영

Deutsche Telekom의 접근에서 두 가지가 돋보입니다.

#### Sovereign Partner Cloud (주권 클라우드)

| 구분 | 내용 |
|------|------|
| **구조** | Deutsche Telekom이 ServiceNow의 주권 파트너 클라우드 제공자로 선정 |
| **목적** | 독일·EU의 규제 산업 고객이 데이터 주권을 유지하면서 ServiceNow 사용 |
| **대상** | 금융, 공공, 의료 등 강한 규제를 받는 조직 |
| **가치** | 국내·EU 데이터 보호법 준수와 글로벌 ITSM 플랫폼의 혜택을 동시에 |

#### Low-code 기반 시민 개발자(Citizen Developer)

| 구분 | 내용 |
|------|------|
| **접근** | Now Platform의 로우코드 기능을 확장해 현업이 직접 워크플로우 생성 |
| **효과** | IT팀이 모든 요구사항을 받아 처리하는 병목을 해소 |
| **거버넌스** | 플랫폼 내 승인·감사·정책이 내재돼 리스크를 제한 |

### 4.3 Deutsche Telekom 사례의 시사점

이 사례는 Part 6의 거버넌스 관점과 직접 연결됩니다.

| 연결 포인트 | 설명 |
|-----------|------|
| **COBIT MEA03** (외부 요구사항 준수) | 주권 클라우드가 규제 대응의 기술적 기반 |
| **COBIT APO13** (보안 관리) | 데이터 주권 보장 |
| **ITIL 5 임베디드 거버넌스** | 로우코드 워크플로우에 승인·감사 내재 |
| **ISO/IEC 20000 적용성** | 통제된 서비스 관리 시스템(SMS) 운영 가능 |

통신사처럼 전기통신사업법, 개인정보보호법, 금융 규제가 겹치는 환경에서 "규제와 효율화를 동시에" 달성하는 방식의 레퍼런스로 활용할 수 있습니다.

---

## 5. Vodafone — 디지털 전환의 핵심 도구

### 5.1 배경과 접근

Vodafone은 구체적 지표 공개는 상대적으로 적지만, **ITSM을 디지털 전환의 일부로 본다**는 관점에서 참고 가치가 있습니다.

| 항목 | 내용 |
|------|------|
| **규모** | 글로벌 통신 그룹 |
| **활용** | ServiceNow를 디지털 전환의 핵심 도구로 활용 |
| **목표** | 고객이 원하는 채널·시간에 서비스 제공 (Channel of Choice) |
| **관점** | ITSM 단독 프로젝트가 아닌 전사 디지털 전환의 한 축 |

### 5.2 Vodafone 사례의 시사점

Vodafone 사례는 **"ITSM을 IT 부서 내부 프로젝트로 한정하지 말라"**는 메시지를 줍니다. Part 1에서 "ITSM·ITOM·ITAM이 연결돼야 한다"고 했던 내용의 한 단계 위 버전으로, **디지털 전환·고객 경험·운영 효율을 모두 ITSM 플랫폼 위에서 엮는 접근**입니다.

---

## 6. 국내 통신사 사례의 제약

SK텔레콤·KT·LG유플러스의 **구체적인 ITSM 성과 지표**는 공개된 영문·국문 자료에서 특정하기 어려웠습니다. 확인 가능한 수준은 다음과 같습니다.

| 국내 통신사 | 확인 내용 | 한계 |
|------------|---------|------|
| **SK텔레콤** | SK C&C가 운영하는 ITSM 체계를 사용하는 고객사로 언급 | 오래된 기사 기반, 현재 상태 확인 필요 |
| **KT** | 개별 ITSM 도입 상세 사례 특정 어려움 | 공개 자료 제한 |
| **LG유플러스** | 개별 ITSM 도입 상세 사례 특정 어려움 | 공개 자료 제한 |

### 국내 사례 확인을 위한 권장 경로

| 경로 | 기대 정보 |
|------|---------|
| ServiceNow Korea 고객 세미나 자료 | 최근 도입 사례 |
| SK C&C, LG CNS, 포스코DX 케이스 스터디 | 구축 파트너 관점의 사례 |
| Gartner Peer Insights 한국 리뷰 | 사용자 관점 평가 |
| 각사 IR 자료 및 기술 블로그 | 간접적 힌트 |

국내 통신사들도 ITSM을 사용하지 않을 리는 없지만, **대외 공개를 적극 하지 않는 경향**이 있습니다. BT처럼 로드맵을 공식 발표한 사례가 오히려 예외에 가깝습니다.

---

## 7. 네 사례의 공통 패턴

네 가지 글로벌 통신사 사례를 시리즈 Part 2~6의 관점에서 분석하면 공통 패턴이 뚜렷합니다.

| 공통 패턴 | 사례 증거 | 시리즈 연결 |
|----------|---------|-----------|
| **레거시 통합부터 시작** | BT 56개 → 1개 통합 | Part 5 "도구 파편화 비용" |
| **CMDB·단일 데이터 모델 선결** | A1·BT 모두 플랫폼 통합 | Part 5 "CMDB 허브" |
| **AIOps·예측 분석은 2단계** | BT AI Ops, A1 예측 분석 | Part 3 + Part 5 |
| **규제·경험·비용의 동시 추구** | Deutsche Telekom 주권 클라우드 | Part 6 거버넌스 |
| **단계별 로드맵** | BT 5년(2022~2027) 계획 | Part 6 "작게 시작" |
| **수치로 측정** | BT 50%·20x·£25M | Part 2 "인시던트는 측정의 최소 단위" |

---

## 8. 실무 활용 가이드

이 사례들을 단순 참고가 아니라 **내부 설득과 로드맵 수립의 재료**로 쓰는 방법입니다.

### 8.1 4단계 활용법

| 단계 | 활동 | 산출물 |
|------|------|--------|
| **1. 현 상태 진단** | 우리 조직의 서비스 관리 도구 개수 파악, 프로세스 파편화 수준 측정 | 도구 인벤토리, 프로세스 맵 |
| **2. 단계 분리** | 통합 → AI → Zero-touch 중 현재 위치 파악 | 성숙도 평가 보고서 |
| **3. 지표 설정** | BT·A1 수치를 참고한 목표 지표 설정 | 목표 KPI 정의서 |
| **4. 5년 로드맵** | 통신사 규모 기대치에 맞는 장기 계획 수립 | 전환 로드맵, 투자 계획 |

### 8.2 내부 설득용 핵심 수치 (BT 사례 기준)

다음 수치들은 내부 경영진·이사회 설득 자료에 활용할 수 있는 검증된 레퍼런스입니다.

| 수치 | 출처 | 활용 맥락 |
|------|------|---------|
| "56 → 1 플랫폼 통합" | BT 2022년 공식 발표 | 레거시 통합의 가치 설명 |
| "변경 배포 속도 20배 개선" | BT 초기 롤아웃 | 변경 관리 자동화의 효과 |
| "서비스 요청 공수 50% 감소" | BT 초기 롤아웃 | 운영 효율 개선 근거 |
| "£25M 5년 절감 목표" | BT 공식 발표 | 재무적 타당성 |

### 8.3 Part 6 거버넌스 로드맵과의 결합

이 사례들은 Part 6의 거버넌스 로드맵(ITIL → COBIT → ISO 20000)과 결합해 **기술·프로세스·거버넌스 세 축의 균형 잡힌 계획**을 세우는 데 활용할 수 있습니다.

| 축 | 사례 연결 |
|----|---------|
| **기술** | BT 단일 플랫폼 통합, Google Cloud 결합 |
| **프로세스** | BT 76개 방식 → 표준화, A1 예측 분석 워크플로우 |
| **거버넌스** | Deutsche Telekom 주권 클라우드, Low-code 통제 |

---

## 9. 시사점 종합 — 시리즈 7편을 관통하는 한 줄

BT의 "56 → 1"이든, A1의 예측 분석이든, Deutsche Telekom의 주권 클라우드든, Vodafone의 고객 채널 통합이든 — **모두 같은 원칙에서 출발합니다.**

> **ITSM·ITOM·ITAM을 따로 떼어 보지 말고, 프로세스·거버넌스·플랫폼의 세 축으로 연결해서 단계적으로 키워라. 그리고 그 과정을 숫자로 측정해라.**

규모와 순서만 다를 뿐, 본질은 동일합니다. 시리즈 Part 1~7에서 다룬 내용을 한 문장으로 압축하면 위와 같습니다.

---

## 10. 약어 정리

| 약어 | 풀네임 | 한 마디로 |
|------|--------|-----------|
| **Zero Ops** | Zero-touch Operations | 사람 개입 없이 운영되는 상태 |
| **AIOps** | AI for IT Operations | AI/ML 기반 IT 운영 자동화 |
| **Predictive Analytics** | - | 과거 데이터 기반 미래 예측 기법 |
| **Sovereign Cloud** | - | 데이터 주권이 보장된 클라우드 |
| **Low-code** | - | 최소 코딩으로 앱·워크플로우 개발 방식 |
| **CSP** | Communication Service Provider | 통신 서비스 제공자 |
| **B2B** | Business to Business | 기업 간 거래 |
| **KPI** | Key Performance Indicator | 핵심 성과 지표 |

---

## 11. 시리즈 전체 목차

| 문서 | 주요 내용 | 상태 |
|------|-----------|------|
| [Part 1: 전체 개요](./confluence-part1-overview.md) | ITSM, ITOM, ITAM 개념과 관계 | 완료 |
| [Part 2: ITSM 상세](./confluence-part2-itsm.md) | 서비스 데스크, SLA, 인시던트/문제/변경 관리 | 완료 |
| [Part 3: ITOM 상세](./confluence-part3-itom.md) | 모니터링, 이벤트 관리, AIOps | 완료 |
| [Part 4: ITAM 상세](./confluence-part4-itam.md) | 자산 관리, 라이선스 최적화, 비용 절감 | 완료 |
| [Part 5: ServiceNow 플랫폼](./confluence-part5-servicenow.md) | ITIL 5, 통합 플랫폼, 도구 비교 | 완료 |
| [Part 6: 거버넌스 체계](./confluence-part6-governance.md) | COBIT, ISO/IEC 20000, 거버넌스 로드맵 | 완료 |
| **Part 7: 통신사 레퍼런스 케이스 (이 글)** | BT, A1 Telekom, Deutsche Telekom, Vodafone 사례 분석 | 완료 |

---

## 12. 출처

본 글의 모든 수치와 사례 내용은 다음 공식 소스에서 검증되었습니다.

- [BT aims for £25m in savings by leaping towards AI-led operations with ServiceNow (BT Newsroom)](https://newsroom.bt.com/bt-aims-for-25m-in-savings-by-leaping-towards-ai-led-operations-with-servicenow/)
- [BT sees $30m+ savings in five years with ServiceNow project (The Register, 2022)](https://www.theregister.com/2022/05/11/bt_servicenow/)
- [BT bets big on AI with ServiceNow to cut legacy baggage (The Register, 2024)](https://www.theregister.com/2024/07/03/bt_servicenow_savings/)
- [BT aims for £25 million in savings with ServiceNow (Intelligent CIO Europe)](https://www.intelligentcio.com/eu/2022/05/12/bt-aims-for-25-million-in-savings-by-leaping-towards-ai-led-operations-with-servicenow/)
- [A1 Telekom — ServiceNow Customer Story](https://www.servicenow.com/customers/a1-telekom.html)
- [A1 Streamlines ITSM and ITOM Processes on ServiceNow (BRIGHT)](https://bright.consulting/casestudies/a1-telekom-servicenow-itsm-and-itom-processes/)
- [Telekom Austria Group Empowers its $4B Business with Cloud-Enabled Digital Service Management (BRIGHT)](https://bright.consulting/casestudies/cloud-enabled-digital-service-management-servicenow-a1-austria/)
- [Deutsche Telekom — ServiceNow Customer Story](https://www.servicenow.com/customers/deutsche-telekom.html)
- [Vodafone — ServiceNow Customer Story](https://www.servicenow.com/customers/vodafone.html)
- [Telefonica Tech UK selects ServiceNow ITSM (Apps Run The World)](https://www.appsruntheworld.com/customers-database/purchases/view/telefonica-tech-uk-united-kingdom-selects-servicenow-itsm-for-it-service-management)

---

궁금한 점이나 국내 사례 공유가 있으면 댓글로 남겨주세요.
