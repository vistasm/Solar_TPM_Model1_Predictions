# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-07 UTC
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
| DEGRADED |   27 |  120.3 | 40.7% | 0.690 | 0.4 |       24 | 0.0% |   0.0% |    - | 45.5% |   0.0833 |
|      ALL |   59 |   66.8 | 37.3% | 0.710 | 0.5 |       55 | 14.3% |  21.4% | 0.6× | 43.9% |   0.2545 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.013 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|       OK |   12 |   33.8 | 0.0% | 0.011 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
| DEGRADED |   27 |  120.3 | 0.0% | 0.005 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |   59 |   66.8 | 0.0% | 0.009 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   20 |   14.2 | 0.0% | 0.606 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |   12 |   33.8 | 0.0% | 0.556 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   27 |  120.3 | 0.0% | 0.451 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
|      ALL |   59 |   66.8 | 0.0% | 0.525 | 0.0 |       55 |    - |   0.0% |    - | 0.0% |   0.0545 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 71.4% | 0.834 | 1.0 |        7 | 20.0% |  50.0% | 0.7× | 80.0% |   0.2857 |
|       OK |    4 |   29.6 | 25.0% | 0.737 | 1.0 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   20 |  143.1 | 30.0% | 0.671 | 0.3 |       17 | 0.0% |   0.0% |    - | 31.2% |   0.0588 |
|      ALL |   31 |   99.2 | 38.7% | 0.716 | 0.6 |       27 | 18.2% |  50.0% | 1.2× | 39.1% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.022 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   29.6 | 0.0% | 0.014 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   20 |  143.1 | 0.0% | 0.005 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   99.2 | 0.0% | 0.010 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   13.5 | 0.0% | 0.723 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   29.6 | 0.0% | 0.565 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  143.1 | 0.0% | 0.448 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   99.2 | 0.0% | 0.525 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available