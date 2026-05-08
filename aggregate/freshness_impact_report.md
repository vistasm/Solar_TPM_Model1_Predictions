# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (33.3%) is 33.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 30.0% | 0.709 | 0.4 |       20 | 33.3% |  22.2% | 0.7× | 36.4% |   0.4500 |
|       OK |   12 |   33.8 | 41.7% | 0.755 | 0.8 |       11 | 20.0% |  33.3% | 0.7× | 50.0% |   0.2727 |
| DEGRADED |   28 |  116.5 | 39.3% | 0.683 | 0.4 |       25 | 0.0% |   0.0% |    - | 47.8% |   0.0800 |
|      ALL |   60 |   65.9 | 36.7% | 0.706 | 0.5 |       56 | 13.6% |  21.4% | 0.6× | 45.2% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.013 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|       OK |   12 |   33.8 | 0.0% | 0.011 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
| DEGRADED |   28 |  116.5 | 0.0% | 0.005 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   60 |   65.9 | 0.0% | 0.009 | 0.0 |       56 |    - |   0.0% |    - | 0.0% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.606 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |   12 |   33.8 | 0.0% | 0.556 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   28 |  116.5 | 0.0% | 0.453 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |
|      ALL |   60 |   65.9 | 0.0% | 0.525 | 0.0 |       56 |    - |   0.0% |    - | 0.0% |   0.0536 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 71.4% | 0.834 | 1.0 |        7 | 20.0% |  50.0% | 0.7× | 80.0% |   0.2857 |
|       OK |    4 |   29.6 | 25.0% | 0.737 | 1.0 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   20 |  141.1 | 30.0% | 0.661 | 0.3 |       17 | 0.0% |   0.0% |    - | 37.5% |   0.0588 |
|      ALL |   31 |   97.9 | 38.7% | 0.710 | 0.6 |       27 | 16.7% |  50.0% | 1.1× | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.022 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   29.6 | 0.0% | 0.014 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   20 |  141.1 | 0.0% | 0.005 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   97.9 | 0.0% | 0.010 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.723 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   29.6 | 0.0% | 0.565 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  141.1 | 0.0% | 0.449 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   97.9 | 0.0% | 0.526 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available