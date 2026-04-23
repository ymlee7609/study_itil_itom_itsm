# Workaround vs Fix vs Root Cause Resolution

"해결했어요"라는 한마디 속에 3가지 다른 상태가 섞여 있다. 임시 조치로 넘기고 근본 해결을 놓치면 동일 장애가 반복된다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 해결 수준의 계층](#2-해결-수준의-계층)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Workaround (임시조치) | Fix (수정) | Root Cause Resolution (근본 원인 해결) |
|------|----------------------|-----------|---------------------------------------|
| **정의** | 원인 제거 없이 **영향을 줄이는 조치** | 해당 **증상을 직접 제거** | **근본 원인**을 제거해 재발 차단 |
| **지속성** | 일시적, 재적용 필요 | 해당 사례 한정 | 영구적 |
| **원인 파악** | 없어도 가능 | 필요 (증상 수준) | **필수** (구조적 이해) |
| **담당** | Incident Management | Incident/Problem | **Problem Management** |
| **예** | 서비스 재시작, 세션 종료 | 설정 한 줄 수정 | 아키텍처 변경, 버그 패치 배포 |

---

## 2. 해결 수준의 계층

```
Level 1: Workaround  ────► 증상만 임시 회피 (원인 남음)
                           예: 재시작, 캐시 비우기

Level 2: Fix         ────► 이 사례 증상 제거
                           예: 잘못된 설정값 수정

Level 3: Resolution  ────► 근본 원인 제거
                           예: 코드 버그 수정, 구조 개선
                           (해당 유형 재발 차단)
```

**중요**: 한 Incident에서 Workaround → Fix → Resolution으로 **단계적 상승**이 이상적. 많은 조직이 Level 1에 머물러 "같은 장애 무한 반복" 패턴에 빠진다.

---

## 3. 실무 예시

### 예시 1: 메모리 누수 API

| 단계 | 조치 | 효과 |
|------|------|------|
| **Workaround** | 1시간마다 자동 재시작 크론 추가 | 장애는 안 보이지만 원인 존재, 크론 유지 필요 |
| **Fix** | 의심되는 캐시 라이브러리 버전 다운그레이드 | 이번 증상 제거, 다른 라이브러리서 재발 가능 |
| **Resolution** | 근본 원인(잘못된 이벤트 리스너 해제 누락) 코드 수정 → 전 서비스 배포 | 해당 유형 완전 차단 |

### 예시 2: 로그인 장애

| 단계 | 조치 |
|------|------|
| Workaround | "브라우저 캐시 지우세요" 안내 |
| Fix | 문제 쿠키의 만료 설정 수정 |
| Resolution | 인증 토큰 만료 정책 재설계, 테스트 케이스 추가 |

### 예시 3: DB 풀 고갈

| 단계 | 조치 |
|------|------|
| Workaround | 풀 크기 증설 (당장 여유 확보) |
| Fix | 누수 쿼리 찾아 close 추가 |
| Resolution | ORM에 Connection Auto-close 강제 규칙 + 린트·테스트 자동화 |

---

## 4. 왜 이 구분이 중요한가

### (1) Known Error DB의 핵심 개념

- **Known Error** = Problem + 원인 파악 + **Workaround 보유**
- Workaround가 있으면 재발 시 MTTR 대폭 단축
- 그러나 **Workaround만 쌓이고 Resolution 0** → 기술부채 누적

### (2) 리포팅 왜곡 방지

| 지표 | Workaround로 종결 | Resolution으로 종결 |
|------|------------------|---------------------|
| MTTR | 낮게 보임 ✓ | 비슷 |
| 재발률 | **높음** ✗ | 낮음 |
| Problem Close 비율 | 왜곡됨 | 정확 |

→ Incident는 Workaround로 빠르게 종결하되, **Problem 티켓은 Resolution까지 열어둬야** 정확한 운영 품질 측정.

### (3) 조직 성숙도 지표

| 수준 | 비율 패턴 |
|------|----------|
| 낮음 | Workaround 80% / Fix 15% / Resolution 5% |
| 중간 | Workaround 50% / Fix 30% / Resolution 20% |
| 높음 | Workaround 20% / Fix 30% / Resolution 50% |

### (4) 기술부채 가시화

- Workaround는 **일시적**이어야 한다는 합의 필요
- "임시인데 5년째 운영" 패턴 경계 → Workaround 보유 기간 SLA 도입 권장
- 예: "모든 Workaround는 90일 이내 Resolution 또는 공식 Accept 필요"

### (5) Blameless Postmortem의 근거

- 포스트모템은 **Resolution 도출**을 목표로 수행
- Workaround 레벨에서 종결하면 포스트모템이 **"누가 재시작 버튼 눌렀나"** 수준으로 끝남
- Root Cause Analysis(RCA) 프레임워크(5 Whys, Ishikawa, Fault Tree)는 모두 Resolution 도달용

---

## 5. 한눈 정리

```
 긴급도 ↑                           근본성 ↓
    │                                  │
    ▼                                  ▼
Workaround ─────► Fix ─────► Resolution
(임시회피)        (증상제거)   (원인제거)

"일단 살려"      "이 건 해결"   "다시는 안 날 것"

Incident 단계    Incident ~     Problem
                 Problem        Management
```

---

## 한 줄 요약

**Workaround는 임시 회피, Fix는 증상 제거, Resolution은 근본 원인 제거.** Workaround로만 버티면 재발 반복. Incident는 Workaround로 빠르게 종결해도, Problem은 Resolution까지 열어둬야 한다.

---

## 관련 문서

- [Incident vs Problem vs Known Error](incident_vs_problem_vs_known_error.md)
- [ITIL 4 핵심 프로세스 심화](../itil4/09-key-processes.md)
- [Change vs Release vs Deployment](change_vs_release_vs_deployment.md)
