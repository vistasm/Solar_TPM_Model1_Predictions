# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-27 UTC
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
|    FRESH |   17 |   13.7 | 23.5% | 0.683 | 0.3 |       14 | 100.0% |  14.3% | 2.0× | 0.0% |   0.5000 |
|       OK |   10 |   33.8 | 50.0% | 0.759 | 1.0 |        9 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |
| DEGRADED |   22 |  134.7 | 40.9% | 0.689 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   49 |   72.2 | 36.7% | 0.702 | 0.5 |       45 | 7.1% |   9.1% | 0.3× | 38.2% |   0.2444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.7 | 0.0% | 0.012 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   10 |   33.8 | 0.0% | 0.011 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.006 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   49 |   72.2 | 0.0% | 0.009 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   13.7 | 0.0% | 0.589 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |   10 |   33.8 | 0.0% | 0.561 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.429 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   49 |   72.2 | 0.0% | 0.511 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 33.3% | 0.687 | 0.4 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    4 |   31.1 | 75.0% | 0.815 | 1.5 |        3 | 0.0% |      - |    - | 66.7% |   0.0000 |
| DEGRADED |   18 |  145.5 | 38.9% | 0.691 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   91.8 | 41.9% | 0.706 | 0.6 |       27 | 0.0% |   0.0% |    - | 39.1% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 0.0% | 0.013 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    4 |   31.1 | 0.0% | 0.025 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   91.8 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   11.4 | 0.0% | 0.701 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   31.1 | 0.0% | 0.725 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.423 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   91.8 | 0.0% | 0.543 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available