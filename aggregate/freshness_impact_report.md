# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (46.7%) is 46.7% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.0%) is 3.0× the overall rate (1.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.5%) is 3.0× the overall rate (0.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   13.0 | 42.5% | 0.738 | 0.9 |       37 | 46.7% |  41.2% | 1.0× | 40.0% |   0.4595 |
|       OK |   22 |   34.5 | 40.9% | 0.716 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  121 |   57.8 | 40.5% | 0.717 | 0.6 |      117 | 17.4% |  26.7% | 0.7× | 43.7% |   0.2564 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   13.0 | 5.0% | 0.056 | 0.1 |       37 | 0.0% |   0.0% |    - | 3.3% |   0.1892 |
|       OK |   22 |   34.5 | 0.0% | 0.009 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  121 |   57.8 | 1.7% | 0.027 | 0.0 |      117 | 0.0% |   0.0% |    - | 0.9% |   0.1026 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   40 |   13.0 | 2.5% | 0.662 | 0.0 |       37 | 0.0% |   0.0% |    - | 3.0% |   0.1081 |
|       OK |   22 |   34.5 | 0.0% | 0.573 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  121 |   57.8 | 0.8% | 0.568 | 0.0 |      117 | 0.0% |   0.0% |    - | 0.9% |   0.0427 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |    9.6 | 72.7% | 0.822 | 2.0 |        8 | 83.3% | 100.0% | 1.3× | 33.3% |   0.6250 |
|       OK |    4 |   28.9 | 25.0% | 0.671 | 0.5 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 37.5% | 0.690 | 0.4 |       16 | 0.0% |   0.0% |    - | 46.2% |   0.1875 |
|      ALL |   31 |   48.5 | 48.4% | 0.735 | 1.0 |       27 | 41.7% |  62.5% | 1.4× | 36.8% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |    9.6 | 18.2% | 0.142 | 0.2 |        8 | 0.0% |   0.0% |    - | 20.0% |   0.3750 |
|       OK |    4 |   28.9 | 0.0% | 0.013 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.043 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   48.5 | 6.5% | 0.074 | 0.1 |       27 | 0.0% |   0.0% |    - | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |    9.6 | 9.1% | 0.812 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|       OK |    4 |   28.9 | 0.0% | 0.615 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.529 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.5 | 3.2% | 0.641 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available