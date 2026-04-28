# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (50.0%) is 50.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   14.3 | 27.8% | 0.697 | 0.4 |       15 | 50.0% |  14.3% | 1.1× | 12.5% |   0.4667 |
|       OK |   10 |   33.8 | 50.0% | 0.759 | 1.0 |        9 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |
| DEGRADED |   22 |  134.7 | 40.9% | 0.689 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   50 |   71.2 | 38.0% | 0.706 | 0.5 |       46 | 6.7% |   9.1% | 0.3× | 40.0% |   0.2391 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   14.3 | 0.0% | 0.012 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |   10 |   33.8 | 0.0% | 0.011 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.006 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   50 |   71.2 | 0.0% | 0.009 | 0.0 |       46 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   18 |   14.3 | 0.0% | 0.600 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   10 |   33.8 | 0.0% | 0.561 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.429 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   50 |   71.2 | 0.0% | 0.517 | 0.0 |       46 |    - |   0.0% |    - | 0.0% |   0.0652 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.5 | 40.0% | 0.711 | 0.6 |        7 | 0.0% |   0.0% |    - | 25.0% |   0.4286 |
|       OK |    3 |   25.7 | 66.7% | 0.798 | 1.7 |        2 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 38.9% | 0.691 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   91.0 | 41.9% | 0.708 | 0.6 |       27 | 0.0% |   0.0% |    - | 39.1% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.5 | 0.0% | 0.013 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.4286 |
|       OK |    3 |   25.7 | 0.0% | 0.017 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   91.0 | 0.0% | 0.009 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.5 | 0.0% | 0.710 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    3 |   25.7 | 0.0% | 0.705 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.423 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   91.0 | 0.0% | 0.543 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available