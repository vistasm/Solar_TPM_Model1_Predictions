# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-15 UTC
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
|    FRESH |   32 |   14.5 | 31.2% | 0.690 | 0.5 |       30 | 20.0% |  16.7% | 0.5× | 44.4% |   0.4000 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       20 | 12.5% |  33.3% | 0.8× | 41.2% |   0.1500 |
| DEGRADED |   45 |  100.9 | 40.0% | 0.705 | 0.4 |       44 | 0.0% |   0.0% |    - | 48.6% |   0.1591 |
|      ALL |   98 |   58.5 | 36.7% | 0.700 | 0.5 |       94 | 8.3% |  13.6% | 0.4× | 45.8% |   0.2340 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.022 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1333 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.0500 |
| DEGRADED |   45 |  100.9 | 0.0% | 0.004 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |   98 |   58.5 | 0.0% | 0.011 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0851 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.600 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  100.9 | 0.0% | 0.492 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |
|      ALL |   98 |   58.5 | 0.0% | 0.543 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0426 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.9 | 27.3% | 0.636 | 0.5 |        9 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
|       OK |    7 |   35.7 | 28.6% | 0.630 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   13 |   79.0 | 46.2% | 0.733 | 0.5 |       12 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   31 |   46.5 | 35.5% | 0.676 | 0.4 |       27 | 0.0% |   0.0% |    - | 52.4% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.9 | 0.0% | 0.004 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   35.7 | 0.0% | 0.008 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   79.0 | 0.0% | 0.003 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   46.5 | 0.0% | 0.005 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.9 | 0.0% | 0.589 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   35.7 | 0.0% | 0.591 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   79.0 | 0.0% | 0.551 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.5 | 0.0% | 0.573 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available