# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-30 UTC
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
|    FRESH |   19 |   14.3 | 31.6% | 0.706 | 0.4 |       16 | 33.3% |  14.3% | 0.8× | 22.2% |   0.4375 |
|       OK |   11 |   34.3 | 45.5% | 0.758 | 0.9 |       10 | 20.0% |  33.3% | 0.7× | 57.1% |   0.3000 |
| DEGRADED |   22 |  134.7 | 40.9% | 0.689 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   52 |   69.5 | 38.5% | 0.710 | 0.5 |       48 | 11.8% |  16.7% | 0.5× | 41.7% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.013 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1875 |
|       OK |   11 |   34.3 | 0.0% | 0.012 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.006 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   52 |   69.5 | 0.0% | 0.010 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.1042 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.609 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   11 |   34.3 | 0.0% | 0.557 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.429 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   52 |   69.5 | 0.0% | 0.522 | 0.0 |       48 |    - |   0.0% |    - | 0.0% |   0.0625 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 55.6% | 0.761 | 0.8 |        6 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
|       OK |    4 |   29.2 | 50.0% | 0.784 | 1.2 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   18 |  145.5 | 38.9% | 0.691 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   92.1 | 45.2% | 0.723 | 0.6 |       27 | 9.1% |  25.0% | 0.6× | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 0.0% | 0.018 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    4 |   29.2 | 0.0% | 0.018 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   92.1 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 0.0% | 0.716 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   29.2 | 0.0% | 0.659 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.423 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   92.1 | 0.0% | 0.538 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available