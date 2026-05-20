# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-20 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (28.6%) is 28.6% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 33.3% | 0.705 | 0.5 |       22 | 28.6% |  20.0% | 0.6× | 41.7% |   0.4545 |
|       OK |   15 |   34.1 | 40.0% | 0.722 | 0.8 |       14 | 16.7% |  33.3% | 0.8× | 45.5% |   0.2143 |
| DEGRADED |   33 |  108.0 | 36.4% | 0.694 | 0.4 |       32 | 0.0% |   0.0% |    - | 42.9% |   0.1250 |
|      ALL |   72 |   61.3 | 36.1% | 0.703 | 0.5 |       68 | 12.0% |  17.6% | 0.5× | 43.1% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1364 |
|       OK |   15 |   34.1 | 0.0% | 0.010 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
| DEGRADED |   33 |  108.0 | 0.0% | 0.004 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   72 |   61.3 | 0.0% | 0.013 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0882 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |   15 |   34.1 | 0.0% | 0.554 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   33 |  108.0 | 0.0% | 0.469 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
|      ALL |   72 |   61.3 | 0.0% | 0.529 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0441 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 70.0% | 0.813 | 1.1 |        8 | 16.7% |  33.3% | 0.4× | 100.0% |   0.3750 |
|       OK |    6 |   29.7 | 33.3% | 0.693 | 1.0 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
| DEGRADED |   15 |  119.1 | 26.7% | 0.688 | 0.3 |       14 | 0.0% |   0.0% |    - | 36.4% |   0.2143 |
|      ALL |   31 |   67.5 | 41.9% | 0.729 | 0.7 |       27 | 16.7% |  28.6% | 0.6× | 50.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.054 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   29.7 | 0.0% | 0.011 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |   15 |  119.1 | 0.0% | 0.002 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   67.5 | 0.0% | 0.021 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.678 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   29.7 | 0.0% | 0.593 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  119.1 | 0.0% | 0.504 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   67.5 | 0.0% | 0.578 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available