# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-04 UTC
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
|       OK |   11 |   34.3 | 45.5% | 0.758 | 0.9 |       11 | 20.0% |  33.3% | 0.7× | 50.0% |   0.2727 |
| DEGRADED |   25 |  124.8 | 44.0% | 0.705 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   56 |   67.5 | 39.3% | 0.717 | 0.5 |       52 | 15.0% |  23.1% | 0.6× | 43.6% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.013 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1579 |
|       OK |   11 |   34.3 | 0.0% | 0.012 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
| DEGRADED |   25 |  124.8 | 0.0% | 0.005 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   56 |   67.5 | 0.0% | 0.009 | 0.0 |       52 |    - |   0.0% |    - | 0.0% |   0.0962 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.606 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1053 |
|       OK |   11 |   34.3 | 0.0% | 0.557 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  124.8 | 0.0% | 0.444 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   56 |   67.5 | 0.0% | 0.524 | 0.0 |       52 |    - |   0.0% |    - | 0.0% |   0.0577 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 71.4% | 0.834 | 1.0 |        6 | 20.0% | 100.0% | 1.2× | 80.0% |   0.1667 |
|       OK |    3 |   30.1 | 33.3% | 0.742 | 1.3 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   21 |  132.1 | 42.9% | 0.710 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   95.5 | 48.4% | 0.741 | 0.7 |       27 | 15.4% |  66.7% | 1.4× | 45.8% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.022 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    3 |   30.1 | 0.0% | 0.018 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   21 |  132.1 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   95.5 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.723 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    3 |   30.1 | 0.0% | 0.573 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  132.1 | 0.0% | 0.442 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   95.5 | 0.0% | 0.518 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available