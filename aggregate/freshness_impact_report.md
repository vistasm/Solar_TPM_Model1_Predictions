# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-06 UTC
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
|    FRESH |   20 |   14.2 | 30.0% | 0.709 | 0.4 |       19 | 33.3% |  25.0% | 0.8× | 36.4% |   0.4211 |
|       OK |   12 |   33.8 | 41.7% | 0.755 | 0.8 |       11 | 20.0% |  33.3% | 0.7× | 50.0% |   0.2727 |
| DEGRADED |   26 |  122.0 | 42.3% | 0.701 | 0.5 |       24 | 0.0% |   0.0% |    - | 45.5% |   0.0833 |
|      ALL |   58 |   66.6 | 37.9% | 0.715 | 0.5 |       54 | 14.3% |  23.1% | 0.6× | 43.9% |   0.2407 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.013 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1579 |
|       OK |   12 |   33.8 | 0.0% | 0.011 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
| DEGRADED |   26 |  122.0 | 0.0% | 0.005 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |   58 |   66.6 | 0.0% | 0.009 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0926 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.606 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1053 |
|       OK |   12 |   33.8 | 0.0% | 0.556 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   26 |  122.0 | 0.0% | 0.448 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |   58 |   66.6 | 0.0% | 0.524 | 0.0 |       54 |    - |   0.0% |    - | 0.0% |   0.0556 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 71.4% | 0.834 | 1.0 |        6 | 20.0% | 100.0% | 1.2× | 80.0% |   0.1667 |
|       OK |    4 |   29.6 | 25.0% | 0.737 | 1.0 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   20 |  140.8 | 35.0% | 0.691 | 0.3 |       18 | 0.0% |   0.0% |    - | 35.3% |   0.0556 |
|      ALL |   31 |   97.7 | 41.9% | 0.729 | 0.6 |       27 | 16.7% |  66.7% | 1.5× | 41.7% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.022 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   29.6 | 0.0% | 0.014 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   20 |  140.8 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   97.7 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.723 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   29.6 | 0.0% | 0.565 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  140.8 | 0.0% | 0.442 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   97.7 | 0.0% | 0.522 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available