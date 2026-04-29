# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-29 UTC
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
|       OK |   10 |   33.8 | 50.0% | 0.759 | 1.0 |        9 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |
| DEGRADED |   22 |  134.7 | 40.9% | 0.689 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   51 |   70.1 | 39.2% | 0.709 | 0.6 |       47 | 6.2% |   9.1% | 0.3× | 41.7% |   0.2340 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.013 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1875 |
|       OK |   10 |   33.8 | 0.0% | 0.011 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.006 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   51 |   70.1 | 0.0% | 0.010 | 0.0 |       47 |    - |   0.0% |    - | 0.0% |   0.0851 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.609 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   10 |   33.8 | 0.0% | 0.561 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.429 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   51 |   70.1 | 0.0% | 0.522 | 0.0 |       47 |    - |   0.0% |    - | 0.0% |   0.0638 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 50.0% | 0.740 | 0.7 |        7 | 0.0% |   0.0% |    - | 40.0% |   0.2857 |
|       OK |    3 |   25.7 | 66.7% | 0.798 | 1.7 |        2 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 38.9% | 0.691 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   90.9 | 45.2% | 0.717 | 0.6 |       27 | 0.0% |   0.0% |    - | 41.7% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 0.0% | 0.017 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    3 |   25.7 | 0.0% | 0.017 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   90.9 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.3 | 0.0% | 0.713 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    3 |   25.7 | 0.0% | 0.705 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.423 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   90.9 | 0.0% | 0.544 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available