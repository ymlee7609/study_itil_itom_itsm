# Governance vs Management

ITIL 5에서 특히 강조되는 구분. 한국어로는 둘 다 "경영"으로 번역되기 쉽지만, **감독(Govern)**과 **실행(Manage)**은 역할·권한·책임이 완전히 다르다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 역할 분리](#2-역할-분리)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Governance (거버넌스) | Management (경영/관리) |
|------|-----------------------|------------------------|
| **정의** | 조직의 **방향 설정·감독·평가** | 방향에 따라 **계획·실행·통제** |
| **어원** | govern (다스리다, 항로를 정하다) | manage (손으로 다루다, 실행) |
| **질문** | "무엇을 할 것인가? 잘 하고 있나?" | "어떻게 할 것인가? 지금 하고 있나?" |
| **주체** | 이사회, CIO, 경영진 | 경영층~실무진 (Line Management) |
| **주기** | 중장기 (분기·연간) | 단기 (일간·주간·월간) |
| **산출** | Policy, Direction, Risk Appetite | Plan, Process, Execution, Report |
| **COBIT 매핑** | EDM (Evaluate, Direct, Monitor) | APO, BAI, DSS, MEA |

---

## 2. 역할 분리

```
          Governance (거버넌스)
        ┌──────────────────────┐
        │  Evaluate  평가      │
        │  Direct    지시      │
        │  Monitor   감독      │
        │  (이사회/경영진)     │
        └──────────┬───────────┘
                   │ 방향 / 정책 / 리스크 수용 한도
                   ▼
        ┌──────────────────────┐
        │  Management (경영)   │
        │  Plan      계획      │
        │  Build     구현      │
        │  Run       운영      │
        │  Monitor   측정      │
        │  (경영층 ~ 실무진)   │
        └──────────┬───────────┘
                   │ 보고 / 성과 / 리스크
                   ▲
          (피드백 루프)
```

**ITIL 4 vs ITIL 5 차이**:
- ITIL 4: 거버넌스가 **작업 "위에서"** 감독
- ITIL 5: 거버넌스가 **작업 "곁에서"** 가이드 — 상시 개입형, AI 거버넌스 강화

---

## 3. 실무 예시

### 예시 1: 클라우드 전환 결정

| 영역 | 내용 |
|------|------|
| **Governance** | 이사회가 "3년 내 클라우드 First 전환, 연 예산 20억 한도, 데이터 국외 이전 금지" 결정 |
| **Management** | CIO·IT팀이 구체 전환 플랜 수립, AWS/Azure 벤더 선정, 단계별 마이그레이션 실행 |
| **Governance 감독** | 분기별 진행 상황 리뷰, 예산·리스크 한도 준수 확인 |

### 예시 2: 보안 정책

| 영역 | 내용 |
|------|------|
| Governance | "Zero Trust 원칙 채택, MFA 전사 필수, 연 보안 투자 최소 5%" |
| Management | IAM 도구 선정, MFA 롤아웃 일정, 예외 승인 프로세스 운영 |
| Governance 점검 | 보안 감사 결과 보고 수령, 주요 사고 리뷰 |

### 예시 3: ITIL vs COBIT

| 영역 | ITIL | COBIT |
|------|------|-------|
| 강점 | Management (서비스 운영 실무) | **Governance** (IT 거버넌스 체계) |
| 관점 | "어떻게 서비스를 잘 운영할까" | "IT가 비즈니스 목표에 기여하게 할까" |
| 실무 조합 | COBIT으로 거버넌스 틀 / ITIL로 관리 실행 |

### 예시 4: AI 도입 (ITIL 5 맥락)

| 영역 | 내용 |
|------|------|
| Governance | "AI는 고객 데이터 외부 학습 금지", "모델 결정은 최종 인간 승인 필요", "연 AI 투자 상한" |
| Management | LLM 벤더 선정, 프롬프트 엔지니어링, 운영 품질 측정, 비용 통제 |
| **ITIL 5 6C 모델** | Context·Capability·Confidence·Control·Collaboration·Continuity → 거버넌스가 관리에 **상시 개입** |

---

## 4. 왜 이 구분이 중요한가

### (1) 책임 소재 명확화

- 거버넌스 실패: 방향 잘못 잡았거나 감독 부재 → **이사회·경영진 책임**
- 관리 실패: 방향은 맞지만 실행 부실 → **관리자·실무자 책임**
- 두 개념 섞이면 **책임 회피·비난 전가** 가능

### (2) 권한·의사결정 체인

| 결정 유형 | 담당 |
|----------|------|
| 리스크 수용 한도 | Governance |
| 리스크 수용 판단 (한도 내) | Management |
| 정책 수립 | Governance |
| 절차 수립 | Management |

### (3) 감사·컴플라이언스 대응

- SOX, ISO 27001, ISMS 등은 **거버넌스 증거** 요구:
  - 이사회 의사록, 리스크 수용 기록
  - 정책 문서, 경영진 서명
- 관리 활동만으로는 컴플라이언스 증명 불가

### (4) 동일 인물이 두 역할을 겸할 때 주의

- CIO는 거버넌스 참여자이자 관리 책임자 → **의사결정 시 모자 구분** 필요
- 거버넌스 회의에서는 "감독자 모자", 실행 회의에서는 "관리자 모자"

### (5) ITIL 5의 핵심 변화

- "작업 위에서 → 작업 곁에서" 거버넌스
- AI와 자동화는 **실시간 의사결정** 요구
- 전통적 분기 거버넌스 회의로는 AI 위험 대응 불가
- → **거버넌스 체계 자체의 속도 향상** 필요

---

## 5. 한눈 정리

```
Governance (감독)              Management (실행)
─────────────────              ──────────────────
"방향을 정하고 감시"             "방향대로 실행"
Evaluate, Direct, Monitor       Plan, Build, Run, Measure
이사회, CIO                     관리자, 실무자
정책, 한도, 리스크 수용          계획, 실행, 보고
분기/연간                      일간/주간/월간
COBIT                          ITIL Management Practices
```

---

## 한 줄 요약

**Governance는 방향 설정·감독(Evaluate·Direct·Monitor), Management는 그 방향대로의 실행(Plan·Build·Run·Measure).** 거버넌스가 없는 관리는 맹목, 관리 없는 거버넌스는 공허. ITIL 5는 거버넌스를 "위"에서 "곁"으로 이동시켰다.

---

## 관련 문서

- [ITIL 4 서비스 가치 시스템 (SVS)](../itil4/03-svs.md)
- [ITIL 5 거버넌스 변화와 경험 관리](../itil5/05-governance-experience.md)
- [Process vs Practice vs Function](process_vs_practice_vs_function.md)
- [Policy vs Standard vs Procedure vs Guideline](policy_vs_standard_vs_procedure.md)
