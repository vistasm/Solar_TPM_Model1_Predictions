# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (28.6%) is 28.6% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   13.9 | 34.8% | 0.722 | 0.5 |       21 | 28.6% |  22.2% | 0.7× | 41.7% |   0.4286 |
|       OK |   15 |   34.1 | 40.0% | 0.722 | 0.8 |       14 | 16.7% |  33.3% | 0.8× | 45.5% |   0.2143 |
| DEGRADED |   32 |  109.8 | 37.5% | 0.693 | 0.4 |       31 | 0.0% |   0.0% |    - | 44.4% |   0.1290 |
|      ALL |   70 |   62.0 | 37.1% | 0.709 | 0.5 |       66 | 12.0% |  18.8% | 0.5× | 44.0% |   0.2424 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   13.9 | 0.0% | 0.028 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   15 |   34.1 | 0.0% | 0.010 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
| DEGRADED |   32 |  109.8 | 0.0% | 0.004 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0645 |
|      ALL |   70 |   62.0 | 0.0% | 0.013 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   13.9 | 0.0% | 0.600 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0952 |
|       OK |   15 |   34.1 | 0.0% | 0.554 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   32 |  109.8 | 0.0% | 0.468 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0323 |
|      ALL |   70 |   62.0 | 0.0% | 0.530 | 0.0 |       66 |    - |   0.0% |    - | 0.0% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.1 | 77.8% | 0.868 | 1.2 |        7 | 16.7% |  50.0% | 0.6× | 100.0% |   0.2857 |
|       OK |    6 |   29.7 | 33.3% | 0.693 | 1.0 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
| DEGRADED |   16 |  136.7 | 25.0% | 0.683 | 0.2 |       15 | 0.0% |   0.0% |    - | 33.3% |   0.2000 |
|      ALL |   31 |   79.8 | 41.9% | 0.739 | 0.7 |       27 | 16.7% |  33.3% | 0.8× | 47.6% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.1 | 0.0% | 0.060 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    6 |   29.7 | 0.0% | 0.011 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |   16 |  136.7 | 0.0% | 0.004 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   79.8 | 0.0% | 0.022 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.1 | 0.0% | 0.697 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    6 |   29.7 | 0.0% | 0.593 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  136.7 | 0.0% | 0.504 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   79.8 | 0.0% | 0.577 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available