# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.2× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.2× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       59 | 41.7% |  47.6% | 1.2× | 36.8% |   0.3559 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       35 | 14.3% |  40.0% | 1.0× | 40.0% |   0.1429 |
| DEGRADED |   98 |   95.0 | 30.6% | 0.652 | 0.3 |       96 | 6.7% |  11.8% | 0.4× | 35.4% |   0.1771 |
|      ALL |  194 |   58.3 | 35.6% | 0.687 | 0.5 |      190 | 20.6% |  32.6% | 0.9× | 36.7% |   0.2263 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       59 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1525 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
| DEGRADED |   98 |   95.0 | 0.0% | 0.011 | 0.0 |       96 |    - |   0.0% |    - | 0.0% |   0.0521 |
|      ALL |  194 |   58.3 | 1.0% | 0.020 | 0.0 |      190 | 50.0% |   6.7% | 6.3× | 0.6% |   0.0789 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       59 | 0.0% |   0.0% |    - | 1.8% |   0.0678 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   98 |   95.0 | 0.0% | 0.508 | 0.0 |       96 |    - |   0.0% |    - | 0.0% |   0.0104 |
|      ALL |  194 |   58.3 | 0.5% | 0.553 | 0.0 |      190 | 0.0% |   0.0% |    - | 0.5% |   0.0263 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 44.4% | 0.650 | 0.4 |        8 | 50.0% | 100.0% | 2.0× | 33.3% |   0.2500 |
|       OK |    4 |   38.9 | 50.0% | 0.686 | 0.5 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   17 |   88.6 | 17.6% | 0.531 | 0.2 |       15 | 33.3% |  33.3% | 1.7× | 16.7% |   0.2000 |
|      ALL |   30 |   59.4 | 30.0% | 0.587 | 0.3 |       26 | 37.5% |  60.0% | 1.9× | 23.8% |   0.1923 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 0.0% | 0.001 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    4 |   38.9 | 0.0% | 0.002 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   88.6 | 0.0% | 0.001 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   59.4 | 0.0% | 0.001 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 0.0% | 0.575 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.557 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   88.6 | 0.0% | 0.535 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   59.4 | 0.0% | 0.550 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available