# Continual vs Continuous Improvement

영어 철자 하나 차이로 의미가 다르다. ITIL은 일관되게 **Continual**을 사용하며, 이는 "끊임없는"이 아니라 **"반복적·간헐적"**을 의미한다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 의미 차이](#2-의미-차이)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Continual (간헐적 반복) | Continuous (끊임없는) |
|------|------------------------|----------------------|
| **어원** | continue (계속하다) + al | continuous (단절 없는) |
| **의미** | **반복적으로** 일어나지만 사이에 **중단·휴지** 있음 | **끊김 없이** 진행 |
| **예** | 분기별 리뷰, 스프린트, PDCA 사이클 | 24시간 가동, 스트리밍 |
| **ITIL 사용** | **Continual Improvement** (공식 용어) | (거의 사용 안 함) |
| **한국어 번역** | 지속적 개선 (반복적 개선이 더 정확) | 연속적, 지속적 |

---

## 2. 의미 차이

```
Continual:
  개선 ─ 휴지 ─ 개선 ─ 휴지 ─ 개선 ─ 휴지 ─ ...
  (반복적이지만 사이에 간격 있음)

Continuous:
  개선━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━...
  (끊김 없이 계속)
```

- **Continual** = **Iterative** (반복적, 간격 있음)
- **Continuous** = **Uninterrupted** (끊김 없음, 실시간)

ITIL의 **Continual Improvement**는 "매일 24시간 개선하라"가 아니라 **"꾸준히 반복해서 개선 사이클을 돌려라"**라는 뜻.

---

## 3. 실무 예시

### 예시 1: ITIL Continual Improvement Model 7단계

```
1. What is the vision?
2. Where are we now?
3. Where do we want to be?
4. How do we get there?
5. Take action
6. Did we get there?
7. How do we keep the momentum?
     │
     ▼
   (다시 1번으로 반복)
```

→ 사이클을 **반복**. 한 사이클 완료 후 다음 사이클까지 **휴지기** 존재 가능.

### 예시 2: 용어 비교

| 맥락 | Continual | Continuous |
|------|-----------|-----------|
| 서비스 개선 | Continual Improvement (ITIL) | - |
| 배포 | - | Continuous Deployment (DevOps) |
| 통합 | - | Continuous Integration (CI) |
| 학습 | Continual Learning | Continuous Learning (ML) |
| 가동 | - | Continuous Operation |
| 모니터링 | - | Continuous Monitoring |

→ **DevOps의 CI/CD는 Continuous** (실시간·끊김 없음). ITIL의 개선은 **Continual** (사이클 반복).

### 예시 3: 실무 번역 혼란

| 한국어 | 영어 대응 | 비고 |
|--------|----------|------|
| "지속적 개선" | Continual Improvement (ITIL) 또는 Continuous Improvement (Lean) | **맥락에 따라 다름** |
| "지속적 통합" | Continuous Integration | DevOps 맥락은 Continuous |
| "지속적 배포" | Continuous Deployment | 동일 |

→ "지속적"이라는 한국어 번역이 두 단어를 덮기 때문에 **영문 원어 병기**가 안전.

---

## 4. 왜 이 구분이 중요한가

### (1) ITIL 시험·자격 정확성

- ITIL 시험은 **Continual Improvement**를 공식 용어로 사용
- "Continuous Improvement"로 쓰면 **철자 오답**으로 감점 (실제 사례 있음)
- Foundation 문제에서 철자 주의 필요

### (2) 조직 문화 차이

| 용어 | 함의 |
|------|------|
| Continual Improvement | "꾸준히 사이클 돌리자" — 현실적, PDCA 적합 |
| Continuous Improvement | "끊임없이 개선" — 번아웃 위험, Kaizen 철학과 유사 |

→ ITIL이 Continual을 쓰는 이유: **"숨 돌릴 틈 있음"** 명시, 무한 개선 강요 방지.

### (3) Lean/Kaizen vs ITIL

- **Kaizen / Lean Six Sigma**: Continuous Improvement 사용 (일본식 지속 철학)
- **ITIL**: Continual Improvement 사용 (반복 사이클 철학)
- 두 프레임워크를 혼용하는 조직은 **용어 통일** 필요

### (4) CI/CD 혼동 방지

- "Continuous Integration"을 ITIL의 Continual과 섞으면 안 됨
- CI/CD는 **소프트웨어 빌드·배포 자동화** (기술적)
- Continual Improvement는 **서비스 관리 품질 개선** (조직적)

### (5) ITIL 5에서도 유지

- ITIL 5 (2026)도 **Continual Improvement** 용어 유지
- "Improve" 활동은 Service Value Chain → PSLM에서도 핵심 활동

---

## 5. 한눈 정리

```
Continual        →  반복 · 간헐적 · 사이클    →  ITIL Improvement
Continuous       →  끊김 없음 · 실시간         →  CI/CD, Monitoring

※ 한국어 "지속적"은 둘 다 덮음 → 영문 병기 권장
※ ITIL 공식 용어는 Continual Improvement
```

---

## 한 줄 요약

**Continual은 "반복적·간헐적"(사이클), Continuous는 "끊김 없는"(실시간).** ITIL은 Continual Improvement를 공식 용어로 쓰며, 이는 "꾸준한 사이클"을 뜻한다. CI/CD의 Continuous와 혼동 주의.

---

## 관련 문서

- [ITIL 4 7대 지도 원칙](../itil4/02-guiding-principles.md)
- [ITIL 4 서비스 가치 시스템 (SVS)](../itil4/03-svs.md)
- [Effectiveness vs Efficiency](effectiveness_vs_efficiency.md)
