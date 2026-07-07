# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.9%) is 42.9% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.1%) is 3.1× the overall rate (1.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.6%) is 3.1× the overall rate (0.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 43.6% | 0.739 | 0.9 |       36 | 42.9% |  37.5% | 1.0× | 40.0% |   0.4444 |
|       OK |   22 |   34.5 | 40.9% | 0.716 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  120 |   58.2 | 40.8% | 0.717 | 0.6 |      116 | 15.6% |  24.1% | 0.6× | 43.7% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 5.1% | 0.058 | 0.1 |       36 |    - |   0.0% |    - | 0.0% |   0.1944 |
|       OK |   22 |   34.5 | 0.0% | 0.009 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  120 |   58.2 | 1.7% | 0.028 | 0.0 |      116 |    - |   0.0% |    - | 0.0% |   0.1034 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.0 | 2.6% | 0.662 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |   22 |   34.5 | 0.0% | 0.573 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  120 |   58.2 | 0.8% | 0.568 | 0.0 |      116 |    - |   0.0% |    - | 0.0% |   0.0431 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |    9.6 | 72.7% | 0.819 | 2.0 |        8 | 80.0% | 100.0% | 1.6× | 25.0% |   0.5000 |
|       OK |    4 |   28.9 | 25.0% | 0.671 | 0.5 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 37.5% | 0.690 | 0.4 |       16 | 0.0% |   0.0% |    - | 46.2% |   0.1875 |
|      ALL |   31 |   48.5 | 48.4% | 0.733 | 1.0 |       27 | 36.4% |  57.1% | 1.4× | 35.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |    9.6 | 18.2% | 0.142 | 0.2 |        8 |    - |   0.0% |    - | 0.0% |   0.3750 |
|       OK |    4 |   28.9 | 0.0% | 0.013 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.043 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   48.5 | 6.5% | 0.074 | 0.1 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |    9.6 | 9.1% | 0.807 | 0.1 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    4 |   28.9 | 0.0% | 0.615 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.529 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.5 | 3.2% | 0.639 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available