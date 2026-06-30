# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (20.0%) is 20.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   14.2 | 33.3% | 0.694 | 0.5 |       32 | 20.0% |  16.7% | 0.5× | 40.0% |   0.3750 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       56 | 0.0% |   0.0% |    - | 46.8% |   0.1607 |
|      ALL |  113 |   61.2 | 37.2% | 0.701 | 0.5 |      109 | 7.5% |  12.5% | 0.3× | 43.5% |   0.2202 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   14.2 | 0.0% | 0.022 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       56 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |  113 |   61.2 | 0.0% | 0.016 | 0.0 |      109 |    - |   0.0% |    - | 0.0% |   0.0826 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   14.2 | 0.0% | 0.603 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0938 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       56 |    - |   0.0% |    - | 0.0% |   0.0179 |
|      ALL |  113 |   61.2 | 0.0% | 0.544 | 0.0 |      109 |    - |   0.0% |    - | 0.0% |   0.0367 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.3 | 37.5% | 0.685 | 0.5 |        7 | 0.0% |   0.0% |    - | 40.0% |   0.2857 |
|       OK |    5 |   36.0 | 40.0% | 0.720 | 0.4 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   18 |   80.4 | 33.3% | 0.677 | 0.4 |       15 | 0.0% |   0.0% |    - | 45.5% |   0.2667 |
|      ALL |   31 |   55.9 | 35.5% | 0.686 | 0.4 |       27 | 0.0% |   0.0% |    - | 42.9% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.3 | 0.0% | 0.009 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   36.0 | 0.0% | 0.012 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   80.4 | 0.0% | 0.038 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   55.9 | 0.0% | 0.027 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.3 | 0.0% | 0.628 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   36.0 | 0.0% | 0.620 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   80.4 | 0.0% | 0.533 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   55.9 | 0.0% | 0.572 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available