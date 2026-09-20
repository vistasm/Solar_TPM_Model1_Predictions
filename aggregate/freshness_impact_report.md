# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-20 UTC
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
|       OK |   35 |   32.9 | 40.0% | 0.722 | 0.6 |       35 | 14.3% |  40.0% | 1.0× | 40.0% |   0.1429 |
| DEGRADED |   97 |   95.4 | 30.9% | 0.652 | 0.3 |       94 | 6.7% |  11.8% | 0.4× | 36.4% |   0.1809 |
|      ALL |  192 |   58.5 | 35.4% | 0.686 | 0.5 |      188 | 20.6% |  32.6% | 0.9× | 37.2% |   0.2287 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       59 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1525 |
|       OK |   35 |   32.9 | 0.0% | 0.013 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
| DEGRADED |   97 |   95.4 | 0.0% | 0.011 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0532 |
|      ALL |  192 |   58.5 | 1.0% | 0.020 | 0.0 |      188 | 50.0% |   6.7% | 6.3× | 0.6% |   0.0798 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       59 | 0.0% |   0.0% |    - | 1.8% |   0.0678 |
|       OK |   35 |   32.9 | 0.0% | 0.557 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   97 |   95.4 | 0.0% | 0.508 | 0.0 |       94 |    - |   0.0% |    - | 0.0% |   0.0106 |
|      ALL |  192 |   58.5 | 0.5% | 0.554 | 0.0 |      188 | 0.0% |   0.0% |    - | 0.5% |   0.0266 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.1 | 50.0% | 0.674 | 0.6 |        9 | 40.0% | 100.0% | 1.8× | 42.9% |   0.2222 |
|       OK |    3 |   40.0 | 33.3% | 0.594 | 0.3 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   17 |   85.9 | 23.5% | 0.545 | 0.3 |       14 | 50.0% |  50.0% | 1.8× | 20.0% |   0.2857 |
|      ALL |   30 |   57.4 | 33.3% | 0.593 | 0.4 |       26 | 40.0% |  66.7% | 1.7× | 30.0% |   0.2308 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.1 | 0.0% | 0.002 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    3 |   40.0 | 0.0% | 0.002 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   85.9 | 0.0% | 0.001 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   57.4 | 0.0% | 0.002 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.1 | 0.0% | 0.580 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   40.0 | 0.0% | 0.566 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   85.9 | 0.0% | 0.539 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   57.4 | 0.0% | 0.555 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available