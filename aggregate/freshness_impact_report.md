# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.2 | 18.8% | 0.666 | 0.2 |       14 | 100.0% |  14.3% | 2.0× | 0.0% |   0.5000 |
|       OK |   10 |   33.8 | 50.0% | 0.759 | 1.0 |        9 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |
| DEGRADED |   22 |  134.7 | 40.9% | 0.689 | 0.5 |       21 | 0.0% |   0.0% |    - | 45.0% |   0.0476 |
|      ALL |   48 |   73.5 | 35.4% | 0.696 | 0.5 |       44 | 7.1% |  10.0% | 0.3× | 38.2% |   0.2273 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.2 | 0.0% | 0.008 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   10 |   33.8 | 0.0% | 0.011 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.006 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   48 |   73.5 | 0.0% | 0.008 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0455 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   14.2 | 0.0% | 0.573 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |   10 |   33.8 | 0.0% | 0.561 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.429 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   48 |   73.5 | 0.0% | 0.504 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.2 | 33.3% | 0.678 | 0.4 |        7 | 100.0% |  25.0% | 1.8× | 0.0% |   0.5714 |
|       OK |    4 |   31.1 | 75.0% | 0.815 | 1.5 |        3 | 0.0% |      - |    - | 66.7% |   0.0000 |
| DEGRADED |   18 |  145.5 | 38.9% | 0.691 | 0.4 |       17 | 0.0% |      - |    - | 41.2% |   0.0000 |
|      ALL |   31 |   92.3 | 41.9% | 0.703 | 0.6 |       27 | 10.0% |  25.0% | 0.7× | 39.1% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.2 | 0.0% | 0.012 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    4 |   31.1 | 0.0% | 0.025 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.006 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.3 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.2 | 0.0% | 0.697 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   31.1 | 0.0% | 0.725 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.423 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.3 | 0.0% | 0.541 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available