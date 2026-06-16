# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (20.0%) is 20.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 31.2% | 0.690 | 0.5 |       31 | 20.0% |  16.7% | 0.5× | 42.1% |   0.3871 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       20 | 12.5% |  33.3% | 0.8× | 41.2% |   0.1500 |
| DEGRADED |   46 |  100.1 | 39.1% | 0.701 | 0.4 |       44 | 0.0% |   0.0% |    - | 48.6% |   0.1591 |
|      ALL |   99 |   58.6 | 36.4% | 0.698 | 0.5 |       95 | 8.3% |  13.6% | 0.4× | 45.2% |   0.2316 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.022 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.1290 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
| DEGRADED |   46 |  100.1 | 0.0% | 0.004 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |   99 |   58.6 | 0.0% | 0.011 | 0.0 |       95 |    - |   0.0% |    - | 0.0% |   0.0842 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.600 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0968 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   46 |  100.1 | 0.0% | 0.488 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |
|      ALL |   99 |   58.6 | 0.0% | 0.541 | 0.0 |       95 |    - |   0.0% |    - | 0.0% |   0.0421 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   15.0 | 30.0% | 0.642 | 0.5 |        9 | 0.0% |   0.0% |    - | 42.9% |   0.2222 |
|       OK |    7 |   35.7 | 28.6% | 0.630 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   14 |   78.0 | 42.9% | 0.719 | 0.4 |       12 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   31 |   48.1 | 35.5% | 0.674 | 0.4 |       27 | 0.0% |   0.0% |    - | 50.0% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   15.0 | 0.0% | 0.005 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   35.7 | 0.0% | 0.008 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   78.0 | 0.0% | 0.003 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   48.1 | 0.0% | 0.004 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   15.0 | 0.0% | 0.593 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   35.7 | 0.0% | 0.591 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   78.0 | 0.0% | 0.534 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.1 | 0.0% | 0.566 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available