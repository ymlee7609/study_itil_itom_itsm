# Process vs Practice vs Function vs Procedure

ITIL v3에서 v4로 넘어오며 용어가 **Process → Practice**로 바뀌어 현장에서 혼선이 많다. 여기에 Function, Procedure까지 섞이면 문서 체계가 무너진다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 포함 관계](#2-포함-관계)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Process (프로세스) | Practice (프랙티스) | Function (기능) | Procedure (절차) |
|------|-------------------|--------------------|-----------------|--------------------|
| **정의** | 입력을 출력으로 변환하는 **활동의 집합** | 작업 수행에 필요한 **조직 자원의 집합** | 특정 활동을 수행하는 **조직 단위** | 프로세스의 **구체적 실행 단계** |
| **ITIL 버전** | v3 중심 (26개 프로세스) | **v4 표준** (34개 프랙티스) | v3 (4개 기능) | 전 버전 공통 |
| **구성 범위** | 활동 + 역할 + 산출물 | Process + 사람 + 도구 + 정보 + 문화 + 파트너 | 사람들(팀/부서) | 구체적 Step-by-Step |
| **예** | Incident Management Process | Incident Management Practice | Service Desk | "긴급 변경 승인 7단계" |

---

## 2. 포함 관계

```
                   Practice (프랙티스)
      ┌──────────────────────────────────────────┐
      │                                          │
      │   Process  +  People  +  Tools  +  Info  │
      │  (절차/활동)  (조직)    (시스템)  (지식)  │
      │       │                                  │
      │       ▼                                  │
      │  Procedure (구체적 실행 단계)             │
      │                                          │
      └──────────────────────────────────────────┘

Function = Practice 내 사람들 묶음 (조직 단위)
```

**핵심**: Practice는 Process의 **상위 개념 + 확장 개념**. Process가 "절차"라면 Practice는 "그 절차를 돌리는 조직 생태계 전체".

---

## 3. 실무 예시

### 예시 1: Incident 처리

| 구분 | 내용 |
|------|------|
| **Process** | 인시던트 접수 → 분류 → 우선순위 지정 → 조사 → 해결 → 종결 (활동 흐름) |
| **Practice** | 위 Process + Service Desk팀 + ServiceNow + KEDB + SLA 문화 + 외주 MSP 계약 |
| **Function** | Service Desk (24×7 운영팀), L2/L3 기술팀 |
| **Procedure** | "우선순위 1 인시던트 에스컬레이션 절차": 15분 내 매니저 통보 → 30분 내 임원 통보 → 고객 공지 작성 |

### 예시 2: Change

| 구분 | 내용 |
|------|------|
| **Practice** | Change Enablement Practice (v4) |
| **Process** | RFC 제출 → 영향 평가 → CAB 승인 → 구현 → 검토 |
| **Function** | Change Manager, CAB (Change Advisory Board) |
| **Procedure** | "Emergency Change 24시간 긴급 승인 절차" |

### 예시 3: v3 vs v4 용어 대응

| ITIL v3 (2007/2011) | ITIL v4 (2019+) | 비고 |
|--------------------|-----------------|------|
| 26 Processes | 34 **Practices** | 개념 확장 |
| 4 Functions (Service Desk, Technical Mgmt, App Mgmt, IT Ops Mgmt) | 명시적 구분 사라짐 | Practice에 흡수 |
| Service Lifecycle (Strategy/Design/Transition/Operation/CSI) | Service Value Chain (6 활동) | 선형 → 네트워크 |

---

## 4. 왜 이 구분이 중요한가

### (1) "Practice로 바뀐 이유"를 놓치면 v4 도입 실패

- v3 Process 관점: "절차 문서 만들고 시행"으로 끝
- v4 Practice 관점: 절차 + 조직 + 도구 + 문화까지 **동시 설계** 필요
- → v3 마인드로 v4 도입 시 "문서만 있고 안 돌아가는" 실패

### (2) Function은 v4에서 사라진 게 아니라 **암시적**

- v3: Service Desk는 별도 Function으로 명시
- v4: Practice 내 "조직 자원"으로 흡수 (여전히 존재, 명칭만 다름)
- 현장에서 "Service Desk 팀"이라는 Function 단위는 **그대로 쓰임**

### (3) Procedure는 실무 실행의 최전선

- Practice와 Process는 추상적
- 실제 운영자는 **Procedure 문서**로 일함
- Procedure가 부실하면 Practice 성숙도 아무 의미 없음

### (4) 문서 체계 계층

```
Policy (정책, 경영진 의지)
  └── Practice (프랙티스, 조직 역량)
        └── Process (프로세스, 활동 흐름)
              └── Procedure (절차, 실행 단계)
                    └── Work Instruction (작업 지시서)
```

→ 문서 명명을 섞으면 **검색·감사·교육 전부 혼선**.

### (5) 컨설팅·감사 커뮤니케이션

- "Incident Process를 개선하자" → v3 어휘, 범위 좁음
- "Incident Practice를 개선하자" → v4 어휘, 조직/도구/문화까지 포함
- 고객·감사인이 사용하는 버전에 맞춰야 대화 가능

---

## 5. 한눈 정리

```
범위 넓음                                                   범위 좁음
    ◄───────────────────────────────────────────────────►

Policy → Practice → Process → Procedure → Work Instruction
          (v4)       (v3)      (실행)      (최하위)
          
                       │
                       ├── 활동 흐름
                       │
                     Function (조직 단위, v3 명시 / v4 암시)
```

---

## 한 줄 요약

**Process는 활동 흐름, Practice는 Process+사람+도구+정보+문화, Function은 조직 단위, Procedure는 구체 실행 단계.** v3→v4에서 Process가 Practice로 확장된 것이 핵심. Function은 명칭만 사라지고 실체는 남아 있다.

---

## 관련 문서

- [ITIL 4 개요](../itil4/01-overview.md)
- [ITIL 4 일반 관리 프랙티스](../itil4/06-practices-general.md)
- [ITIL 4 서비스 관리 프랙티스](../itil4/07-practices-service.md)
- [Policy vs Standard vs Procedure vs Guideline](policy_vs_standard_vs_procedure.md)
- [Governance vs Management](governance_vs_management.md)
