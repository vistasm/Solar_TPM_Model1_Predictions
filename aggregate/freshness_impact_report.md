# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (25.0%) is 25.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 33.3% | 0.705 | 0.5 |       23 | 25.0% |  20.0% | 0.6× | 46.2% |   0.4348 |
|       OK |   16 |   34.6 | 37.5% | 0.700 | 0.8 |       14 | 16.7% |  33.3% | 0.8× | 45.5% |   0.2143 |
| DEGRADED |   33 |  108.0 | 36.4% | 0.694 | 0.4 |       32 | 0.0% |   0.0% |    - | 42.9% |   0.1250 |
|      ALL |   73 |   61.0 | 35.6% | 0.699 | 0.5 |       69 | 11.5% |  17.6% | 0.5× | 44.2% |   0.2464 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.1304 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
| DEGRADED |   33 |  108.0 | 0.0% | 0.004 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   73 |   61.0 | 0.0% | 0.013 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  108.0 | 0.0% | 0.469 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
|      ALL |   73 |   61.0 | 0.0% | 0.529 | 0.0 |       69 |    - |   0.0% |    - | 0.0% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 70.0% | 0.813 | 1.1 |        9 | 14.3% |  33.3% | 0.4× | 100.0% |   0.3333 |
|       OK |    7 |   31.7 | 28.6% | 0.648 | 0.9 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
| DEGRADED |   14 |  109.0 | 28.6% | 0.707 | 0.3 |       13 | 0.0% |   0.0% |    - | 40.0% |   0.2308 |
|      ALL |   31 |   60.5 | 41.9% | 0.728 | 0.7 |       27 | 15.4% |  28.6% | 0.6× | 55.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.054 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   31.7 | 0.0% | 0.010 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |   14 |  109.0 | 0.0% | 0.002 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   31 |   60.5 | 0.0% | 0.021 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.678 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   31.7 | 0.0% | 0.582 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |  109.0 | 0.0% | 0.519 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   60.5 | 0.0% | 0.585 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available