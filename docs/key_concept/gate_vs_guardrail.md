# Gate vs Guardrail

Change Enablement의 **핵심 패러다임 변화**. 전통 ITIL이 "Gate(관문 심사)"에 의존했다면, ITIL 5·DevOps·SRE는 "Guardrail(자동 경계)"로 이동 중이다. 둘을 혼용하면 속도와 통제 둘 다 잃는다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 작동 방식 비교](#2-작동-방식-비교)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 언제 Gate, 언제 Guardrail?](#5-언제-gate-언제-guardrail)
- [6. 한눈 정리](#6-한눈-정리)

---

## 1. 공식 정의

| 구분 | Gate (관문) | Guardrail (가드레일) |
|------|-----------|---------------------|
| **비유** | 톨게이트 — 차를 **멈추고** 통행권 확인 | 고속도로 가드레일 — 차가 **달리되** 이탈만 차단 |
| **정의** | 작업 진행 전 **명시적 승인**이 필요한 통과 지점 | 작업이 자유롭게 진행되도록 하되, **경계 이탈 시에만** 차단하는 자동 규칙 |
| **시점** | **사전 승인** (Before the fact) | **실시간 또는 즉시 탐지** (During the fact) |
| **통과 방식** | 인간 심사 → 통과/기각 | 규칙 충족 → 자동 허용 |
| **기본값** | **차단**이 기본 (승인받아야 진행) | **허용**이 기본 (이탈만 차단) |
| **관련 담당** | CAB, Change Authority, QA 게이트키퍼 | 플랫폼 엔지니어, SRE, Policy-as-Code |
| **실패 처리** | 문서·회의로 재승인 | 자동 롤백·알람·Exception 로깅 |

---

## 2. 작동 방식 비교

```
Gate 방식 (전통)
─────────────────
개발 ──────► [CAB 승인] ──(대기)──► [QA 승인] ──(대기)──► 배포
              │                     │
           심사 회의               테스트 결과 리뷰
           수일~수주                수시간~수일

           "기본값 = 차단. 통과 허락 받아라."


Guardrail 방식 (현대)
────────────────────
개발 ─► CI/CD ─► 자동 정책 검증 ─► 배포 ─► 런타임 정책 감시
              (자동)            (자동)       (자동)
              · 보안 스캔          · 카나리 배포   · SLO 위반 시 롤백
              · 라이선스 체크      · Canary 지표  · Policy-as-Code
              · IaC 표준 검증      · Error Budget

        "기본값 = 허용. 경계를 넘으면 그때 차단."
```

---

## 3. 실무 예시

### 예시 1: Kubernetes 운영 환경 배포

| 접근 | 방식 |
|------|------|
| **Gate** | 매 배포마다 CAB 승인 → 평균 3일 소요, 월 배포 10회 한계 |
| **Guardrail** | OPA(Open Policy Agent)로 정책 자동 검증: (1) 이미지 서명 확인 (2) 리소스 한도 강제 (3) 네트워크 정책 필수 → 정책 위반 시에만 배포 차단 → 일 배포 수십 회 가능 |

### 예시 2: IAM 권한 부여

| 접근 | 방식 |
|------|------|
| Gate | 모든 권한 요청 → 보안팀 개별 검토·승인 (평균 5영업일) |
| Guardrail | SCP(Service Control Policy)로 **금지 권한 범위** 자동 차단 (예: 프로덕션 루트 키 접근 절대 불가). 그 외는 **자가 신청 → 자동 승인** (5분) |

### 예시 3: 데이터베이스 스키마 변경

| 접근 | 방식 |
|------|------|
| Gate | DBA 수동 리뷰 → CAB 승인 → 주말 배포 |
| Guardrail | 자동 검증: (1) 마이그레이션 스크립트 린트 (2) 롤백 스크립트 필수 (3) Shadow DB에서 테스트 자동 실행 (4) 대형 테이블 NOT NULL ADD는 온라인 DDL 강제 → 통과 시 자동 배포 |

### 예시 4: Change Enablement 3단계 분류 (Guardrail 지원)

ITIL 4/5의 Change 분류:

| 유형 | Gate/Guardrail |
|------|---------------|
| **Standard Change** (사전 승인된 반복적 변경) | Guardrail 중심 — 카탈로그 화이트리스트 |
| **Normal Change** | Gate (CAB 심사) + Guardrail (자동 체크) 혼합 |
| **Emergency Change** | Gate (eCAB 긴급) + Guardrail (배포 후 자동 모니터) |

---

## 4. 왜 이 구분이 중요한가

### (1) 속도와 통제의 양립

| 접근 | 속도 | 통제 |
|------|------|------|
| Gate만 | **느림** (대기 시간 주도) | 강하지만 Gate 통과 후 무감시 |
| Guardrail만 | **빠름** | 경계 설계 미흡 시 구멍 |
| **Gate + Guardrail 조합** | 중요 결정만 Gate, 나머지는 Guardrail | **둘 다 확보** |

현대 조직의 해법: **Gate를 최소화**, **Guardrail을 최대화**.

### (2) "CAB 무용론" 논쟁의 중심

- DevOps 진영: "CAB은 속도 저해, 실효성 없다" → DORA 연구도 "CAB은 안정성 개선 효과 없음" 결과 발표
- ITIL 전통 진영: "통제 없이 프로덕션은 불가능"
- **ITIL 5의 해답**: CAB은 **특수 Change만**, 나머지는 Guardrail로 자동화
- → CAB 완전 폐지가 아닌 **역할 축소·재정의**

### (3) Policy-as-Code의 부상

Guardrail의 실체 = **코드화된 정책**:
- OPA (Open Policy Agent): Kubernetes·Terraform 정책
- AWS Config Rules / Azure Policy: 클라우드 가드레일
- HashiCorp Sentinel: Terraform Cloud
- GitHub Actions / GitLab CI: 파이프라인 정책

→ 가드레일은 **문서가 아니라 실행 가능한 코드**.

### (4) "Shift Left"와의 연결

- **Gate** = 나중에 검사 (Shift Right)
- **Guardrail** = 작업 도중에 검사 (Shift Left)
- 버그/위반을 **개발 초기**에 잡을수록 수정 비용 1/10~1/100

### (5) Error Budget과의 상보성

SRE의 Error Budget은 **런타임 Guardrail**:
- SLO 99.9% 목표 → 월 43분 다운타임 예산
- 예산 내: 배포 자유 (Guardrail 통과)
- 예산 초과: 배포 동결 (Guardrail 발동)
- → "Gate 없이도" 위험 관리 가능

### (6) 감사·컴플라이언스에서의 인정

- 과거: 감사관은 Gate의 **서명·의사록** 중심 점검
- 현재: Guardrail의 **자동 로그·Policy-as-Code 증거** 인정
- ISO 27001, SOC 2, PCI-DSS 모두 **자동화된 통제** 인정
- → 수동 Gate 없이도 컴플라이언스 가능

### (7) ITIL 5 거버넌스 변화와 직결

- ITIL 4: 거버넌스가 "작업 **위에서**" (Gate 지향)
- ITIL 5: 거버넌스가 "작업 **곁에서**" (Guardrail 지향)
- AI 거버넌스 6C 모델 (Context·Capability·Confidence·Control·Collaboration·Continuity)도 **상시 개입형** Guardrail 설계

---

## 5. 언제 Gate, 언제 Guardrail?

### Gate가 적절한 경우

- 변경의 **영향이 비가역적** (예: 데이터 완전 삭제, 계약 체결)
- 변경이 **드물고 중대**함 (예: 핵심 아키텍처 변경, 연간 1~2회)
- **법적·규제적 심사**가 명시 요구됨 (예: 의료기기 임상 승인)
- 자동화로 **판단할 수 없는 맥락적 리스크** 존재

### Guardrail이 적절한 경우

- 변경이 **반복적·고빈도** (예: 코드 배포, 설정 변경)
- **정량적 기준**으로 판단 가능 (예: 테스트 커버리지, 보안 스캔 결과)
- **빠른 롤백이 가능**한 환경 (예: Kubernetes, Blue-Green 배포)
- 변경 **표준 패턴이 확립**됨 (예: CRUD API 배포)

### 혼합 (현실적 해법)

| Change 유형 | Gate | Guardrail |
|------------|------|-----------|
| Standard (반복) | 없음 | ✓ (자동 검증) |
| Normal (일반) | 경량 (비동기 리뷰) | ✓ (CI/CD 체크) |
| Major (중대) | ✓ (CAB 심사) | ✓ (배포 후 모니터) |
| Emergency (긴급) | 사후 Gate | ✓ (런타임 감시) |

---

## 6. 한눈 정리

```
Gate (관문)                      Guardrail (가드레일)
───────────                      ────────────────────
"멈추고 허가받아라"                 "달리되, 이탈만 차단"
기본값 = 차단                      기본값 = 허용
사전 승인                         실시간 자동 감시
인간 심사 (CAB)                   Policy-as-Code (OPA 등)
수일~수주                         초~분
Shift Right                      Shift Left
ITIL 4 전통                      ITIL 5 / DevOps / SRE

    ▼                                 ▼
중대·비가역·저빈도 변경            반복·표준·고빈도 변경
(아키텍처, 법적 심사)              (코드 배포, 설정 변경)
```

---

## 한 줄 요약

**Gate는 사전 승인(멈추고 허가받음), Guardrail은 자동 경계(달리되 이탈만 차단).** 전통 ITIL은 Gate 중심, ITIL 5·DevOps·SRE는 Guardrail 중심. 현대 조직의 해법은 **중대 변경만 Gate로, 나머지는 Guardrail(Policy-as-Code)로** 자동화하는 것.

---

## 관련 문서

- [Change vs Release vs Deployment](change_vs_release_vs_deployment.md)
- [Governance vs Management](governance_vs_management.md)
- [Policy vs Standard vs Procedure vs Guideline](policy_vs_standard_vs_procedure.md)
- [Process vs Practice vs Function](process_vs_practice_vs_function.md)
- [ITIL 5 거버넌스 변화와 경험 관리](../itil5/05-governance-experience.md)
- [ITIL 4 vs ITIL 5 종합 비교](../itil4-vs-itil5/01-comprehensive-comparison.md)
