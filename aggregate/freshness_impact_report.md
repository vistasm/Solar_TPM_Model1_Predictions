# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-17 UTC
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
|       OK |   14 |   34.6 | 42.9% | 0.743 | 0.9 |       14 | 16.7% |  33.3% | 0.8× | 45.5% |   0.2143 |
| DEGRADED |   32 |  109.8 | 37.5% | 0.693 | 0.4 |       30 | 0.0% |   0.0% |    - | 42.3% |   0.1333 |
|      ALL |   69 |   62.6 | 37.7% | 0.713 | 0.5 |       65 | 12.5% |  18.8% | 0.5× | 42.9% |   0.2462 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   13.9 | 0.0% | 0.028 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   14 |   34.6 | 0.0% | 0.010 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
| DEGRADED |   32 |  109.8 | 0.0% | 0.004 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   69 |   62.6 | 0.0% | 0.014 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0923 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   23 |   13.9 | 0.0% | 0.600 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0952 |
|       OK |   14 |   34.6 | 0.0% | 0.556 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   32 |  109.8 | 0.0% | 0.468 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0333 |
|      ALL |   69 |   62.6 | 0.0% | 0.530 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.1 | 77.8% | 0.868 | 1.2 |        7 | 16.7% |  50.0% | 0.6× | 100.0% |   0.2857 |
|       OK |    5 |   30.5 | 40.0% | 0.746 | 1.2 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
| DEGRADED |   17 |  139.7 | 23.5% | 0.674 | 0.2 |       15 | 0.0% |   0.0% |    - | 25.0% |   0.2000 |
|      ALL |   31 |   85.1 | 41.9% | 0.742 | 0.7 |       27 | 18.2% |  33.3% | 0.8× | 42.9% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.1 | 0.0% | 0.060 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   30.5 | 0.0% | 0.014 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
| DEGRADED |   17 |  139.7 | 0.0% | 0.006 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   85.1 | 0.0% | 0.023 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.1 | 0.0% | 0.697 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   30.5 | 0.0% | 0.608 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  139.7 | 0.0% | 0.496 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   85.1 | 0.0% | 0.572 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available