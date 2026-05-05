# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-05 UTC
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
| DEGRADED |   25 |  124.8 | 44.0% | 0.705 | 0.5 |       23 | 0.0% |   0.0% |    - | 47.6% |   0.0870 |
|      ALL |   57 |   66.8 | 38.6% | 0.717 | 0.5 |       53 | 14.3% |  23.1% | 0.6× | 45.0% |   0.2453 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.013 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1579 |
|       OK |   12 |   33.8 | 0.0% | 0.011 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
| DEGRADED |   25 |  124.8 | 0.0% | 0.005 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   57 |   66.8 | 0.0% | 0.009 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0943 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.606 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1053 |
|       OK |   12 |   33.8 | 0.0% | 0.556 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  124.8 | 0.0% | 0.444 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   57 |   66.8 | 0.0% | 0.524 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0566 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 71.4% | 0.834 | 1.0 |        6 | 20.0% | 100.0% | 1.2× | 80.0% |   0.1667 |
|       OK |    4 |   29.6 | 25.0% | 0.737 | 1.0 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   20 |  138.5 | 40.0% | 0.703 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   96.2 | 45.2% | 0.737 | 0.6 |       27 | 15.4% |  66.7% | 1.4× | 45.8% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.022 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   29.6 | 0.0% | 0.014 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   20 |  138.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   96.2 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.723 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   29.6 | 0.0% | 0.565 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  138.5 | 0.0% | 0.439 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   96.2 | 0.0% | 0.520 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available