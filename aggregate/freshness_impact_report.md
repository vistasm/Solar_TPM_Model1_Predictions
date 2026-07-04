# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (27.3%) is 27.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (2.7%) is 3.2× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.7%) is 3.2× the overall rate (0.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   13.3 | 40.5% | 0.725 | 0.8 |       33 | 27.3% |  23.1% | 0.7× | 40.0% |   0.3939 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  117 |   59.3 | 39.3% | 0.710 | 0.6 |      113 | 9.5% |  15.4% | 0.4× | 43.7% |   0.2301 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   13.3 | 2.7% | 0.045 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.1515 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  117 |   59.3 | 0.9% | 0.023 | 0.0 |      113 |    - |   0.0% |    - | 0.0% |   0.0885 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   13.3 | 2.7% | 0.645 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.1212 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  117 |   59.3 | 0.9% | 0.560 | 0.0 |      113 |    - |   0.0% |    - | 0.0% |   0.0442 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.4 | 63.6% | 0.791 | 1.6 |        7 | 33.3% |  50.0% | 1.2× | 40.0% |   0.2857 |
|       OK |    4 |   33.3 | 25.0% | 0.662 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 37.5% | 0.690 | 0.4 |       16 | 0.0% |   0.0% |    - | 46.2% |   0.1875 |
|      ALL |   31 |   49.7 | 45.2% | 0.722 | 0.8 |       27 | 10.0% |  20.0% | 0.5× | 40.9% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.4 | 9.1% | 0.093 | 0.1 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   33.3 | 0.0% | 0.014 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.043 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   49.7 | 3.2% | 0.057 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.4 | 9.1% | 0.774 | 0.1 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   33.3 | 0.0% | 0.632 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.529 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.7 | 3.2% | 0.629 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available