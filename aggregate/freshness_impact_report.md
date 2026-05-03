# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-03 UTC
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
|       OK |   11 |   34.3 | 45.5% | 0.758 | 0.9 |       10 | 20.0% |  33.3% | 0.7× | 57.1% |   0.3000 |
| DEGRADED |   24 |  129.8 | 41.7% | 0.698 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   55 |   68.7 | 38.2% | 0.714 | 0.5 |       51 | 15.0% |  23.1% | 0.6× | 44.7% |   0.2549 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.013 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1579 |
|       OK |   11 |   34.3 | 0.0% | 0.012 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
| DEGRADED |   24 |  129.8 | 0.0% | 0.005 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   55 |   68.7 | 0.0% | 0.009 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0980 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.606 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.1053 |
|       OK |   11 |   34.3 | 0.0% | 0.557 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  129.8 | 0.0% | 0.439 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   55 |   68.7 | 0.0% | 0.523 | 0.0 |       51 |    - |   0.0% |    - | 0.0% |   0.0588 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.2 | 62.5% | 0.797 | 0.9 |        7 | 20.0% |  50.0% | 0.7× | 80.0% |   0.2857 |
|       OK |    3 |   30.1 | 33.3% | 0.742 | 1.3 |        2 | 100.0% | 100.0% | 2.0× | 0.0% |   0.5000 |
| DEGRADED |   20 |  138.5 | 40.0% | 0.702 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   95.7 | 45.2% | 0.730 | 0.6 |       27 | 15.4% |  50.0% | 1.0× | 47.8% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.2 | 0.0% | 0.021 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    3 |   30.1 | 0.0% | 0.018 | 0.0 |        2 |    - |   0.0% |    - | 0.0% |   0.5000 |
| DEGRADED |   20 |  138.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   95.7 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.2 | 0.0% | 0.700 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    3 |   30.1 | 0.0% | 0.573 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  138.5 | 0.0% | 0.436 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   95.7 | 0.0% | 0.517 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available