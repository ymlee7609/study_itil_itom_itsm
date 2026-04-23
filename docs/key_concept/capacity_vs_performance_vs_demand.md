# Capacity vs Performance vs Demand

Capacity Management의 3대 변수. "용량이 부족하다"는 한마디 속에 어느 게 문제인지 구분해야 정확한 대응이 가능하다.

## 목차

- [1. 공식 정의](#1-공식-정의)
- [2. 3자 균형](#2-3자-균형)
- [3. 실무 예시](#3-실무-예시)
- [4. 왜 이 구분이 중요한가](#4-왜-이-구분이-중요한가)
- [5. 한눈 정리](#5-한눈-정리)

---

## 1. 공식 정의

| 구분 | Capacity (용량) | Performance (성능) | Demand (수요) |
|------|----------------|--------------------|---------------|
| **정의** | 시스템이 **처리할 수 있는 최대 능력** | 시스템이 **실제로 작업을 수행하는 속도·품질** | 사용자/서비스의 **요구량** |
| **관점** | 공급 측 능력 | 사용자 체감 | 요구량 |
| **예** | CPU 16코어, 초당 1만 TPS 처리 가능 | 응답시간 200ms, 처리량 8천 TPS | 피크타임 초당 9천 요청 |
| **단위** | 자원 총량 | 응답시간·처리율 | 요청량·사용자 수 |

---

## 2. 3자 균형

```
       Demand (수요)
           │
           │ 수요가 증가하면
           ▼
     Capacity (용량) ◄────── 용량 부족 시 성능 저하
           │
           │ 충분한 용량 위에서
           ▼
     Performance (성능)   ◄── 사용자 체감
```

**관계**:
- Demand ≤ Capacity → Performance 양호
- Demand > Capacity → Performance 저하
- Capacity ≫ Demand → Performance 양호지만 **자원 낭비 (과투자)**

---

## 3. 실무 예시

### 예시 1: 이커머스 블랙프라이데이

| 시점 | Demand | Capacity | Performance |
|------|--------|----------|-------------|
| 평상시 | 초당 500 요청 | 초당 5,000 처리 가능 | 응답 120ms ✓ |
| 세일 시작 | 초당 8,000 요청 | 초당 5,000 (변동 없음) | 응답 3초 ✗ (용량 부족) |
| 대응 | - | Auto-scaling으로 15,000까지 확장 | 응답 150ms ✓ |

### 예시 2: DB 응답 느림

| 증상 | 진단 대상 |
|------|----------|
| 쿼리 1건 느림 (1초 →10초) | **Performance** (인덱스·쿼리 튜닝) |
| 동시 쿼리 증가 시 느림 | **Capacity** (CPU·메모리 증설) |
| 특정 배치 시간에만 느림 | **Demand 패턴** (스케줄 조정) |

### 예시 3: 네트워크

| 구분 | 예 |
|------|-----|
| Demand | 피크 대역폭 8Gbps |
| Capacity | 회선 10Gbps |
| Performance | Latency 5ms, Jitter 1ms |

---

## 4. 왜 이 구분이 중요한가

### (1) 문제 진단의 출발점

"느려요" 신고 → 세 가지를 구분해야 올바른 대응:
- Capacity 문제 → 자원 증설
- Performance 문제 → 튜닝·최적화
- Demand 문제 → 부하 분산·스케줄링·제한

### (2) 투자 결정

- Capacity만 늘리기는 **쉬운 길** → 비용 증가
- Performance 튜닝 → 기존 Capacity 그대로 유지 가능
- Demand 관리(캐시·CDN·속도 제한) → 근본 부하 감소

우선순위: **Demand 관리 > Performance 최적화 > Capacity 증설** (비용 효율 순)

### (3) Capacity Management 프랙티스 3축

ITIL Capacity & Performance Management는 3개 서브프로세스:
- Business Capacity Management (비즈니스 성장 예측 → **Demand** 예측)
- Service Capacity Management (서비스 성능 측정 → **Performance** 모니터링)
- Component Capacity Management (하드웨어 용량 → **Capacity** 관리)

### (4) Cloud 시대의 Capacity 개념 변화

- 전통: Capacity = 고정 자원 (사전 구매)
- Cloud: Capacity = **탄력적** (Auto-scaling)
- → Demand 예측 정확도가 비용 결정

### (5) Performance 저하의 숨은 원인

Capacity가 충분해도 Performance 저하:
- 소프트웨어 병목 (락 경합, 비효율 알고리즘)
- 외부 의존성 (느린 외부 API)
- 데이터 구조 (인덱스 부재, 카디널리티 문제)

→ **Capacity 증설로 해결 안 되는 성능 문제** 다수.

---

## 5. 한눈 정리

```
Demand (요구량)  ──► Capacity (능력) ──► Performance (체감)
  예측             공급                  결과
  
Demand 관리:  캐시, CDN, 속도 제한, 오프피크 유도
Capacity 관리: 자원 증설, Auto-scaling
Performance 관리: 코드 최적화, 쿼리 튜닝, 아키텍처 개선
```

---

## 한 줄 요약

**Capacity는 공급 능력, Performance는 실제 체감 속도, Demand는 요구량.** "느려요" 문제는 셋 중 어디인지 구분해야 올바른 해결 가능. 비용 효율 순서: Demand 관리 > Performance 튜닝 > Capacity 증설.

---

## 관련 문서

- [Availability vs Reliability vs Maintainability](availability_vs_reliability_vs_maintainability.md)
- [MTBF vs MTTR vs MTTF](mtbf_vs_mttr_vs_mttf.md)
- [ITIL 4 서비스 관리 프랙티스](../itil4/07-practices-service.md)
- [ITOM 핵심 역량](../itom/03-capabilities.md)
