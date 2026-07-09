# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (50.0%) is 50.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.9%) is 3.0× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.4%) is 3.0× the overall rate (0.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   13.0 | 41.5% | 0.735 | 0.9 |       38 | 50.0% |  44.4% | 1.1× | 40.0% |   0.4737 |
|       OK |   22 |   34.5 | 40.9% | 0.716 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  122 |   57.4 | 40.2% | 0.716 | 0.6 |      118 | 19.1% |  29.0% | 0.7× | 43.7% |   0.2627 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   13.0 | 4.9% | 0.055 | 0.1 |       38 | 50.0% |  12.5% | 2.4× | 3.3% |   0.2105 |
|       OK |   22 |   34.5 | 0.0% | 0.009 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  122 |   57.4 | 1.6% | 0.027 | 0.0 |      118 | 50.0% |   7.7% | 4.5× | 0.9% |   0.1102 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   41 |   13.0 | 2.4% | 0.660 | 0.0 |       38 | 0.0% |   0.0% |    - | 2.9% |   0.1053 |
|       OK |   22 |   34.5 | 0.0% | 0.573 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  122 |   57.4 | 0.8% | 0.569 | 0.0 |      118 | 0.0% |   0.0% |    - | 0.9% |   0.0424 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.8 | 66.7% | 0.806 | 1.8 |        9 | 85.7% | 100.0% | 1.3× | 33.3% |   0.6667 |
|       OK |    3 |   25.3 | 33.3% | 0.686 | 0.7 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 37.5% | 0.690 | 0.4 |       16 | 0.0% |   0.0% |    - | 46.2% |   0.1875 |
|      ALL |   31 |   47.6 | 48.4% | 0.735 | 1.0 |       27 | 46.2% |  66.7% | 1.4× | 38.9% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.8 | 16.7% | 0.130 | 0.2 |        9 | 50.0% |  25.0% | 1.1× | 20.0% |   0.4444 |
|       OK |    3 |   25.3 | 0.0% | 0.001 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.043 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   47.6 | 6.5% | 0.073 | 0.1 |       27 | 50.0% |  20.0% | 2.7× | 4.5% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |    9.8 | 8.3% | 0.794 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    3 |   25.3 | 0.0% | 0.613 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.529 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.6 | 3.2% | 0.640 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available