# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 3.3× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.3× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   13.7 | 39.2% | 0.731 | 0.8 |       50 | 42.1% |  42.1% | 1.1× | 35.5% |   0.3800 |
|       OK |   32 |   32.3 | 40.6% | 0.734 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   83 |   95.4 | 34.9% | 0.681 | 0.4 |       80 | 0.0% |   0.0% |    - | 38.8% |   0.1625 |
|      ALL |  166 |   58.1 | 37.4% | 0.707 | 0.6 |      162 | 17.2% |  27.0% | 0.8× | 38.4% |   0.2284 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   13.7 | 3.9% | 0.045 | 0.0 |       50 | 50.0% |  12.5% | 3.1× | 2.4% |   0.1600 |
|       OK |   32 |   32.3 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.013 | 0.0 |       80 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  166 |   58.1 | 1.2% | 0.023 | 0.0 |      162 | 50.0% |   7.1% | 5.8× | 0.7% |   0.0864 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   13.7 | 2.0% | 0.635 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.2% |   0.0800 |
|       OK |   32 |   32.3 | 0.0% | 0.557 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.504 | 0.0 |       80 |    - |   0.0% |    - | 0.0% |   0.0125 |
|      ALL |  166 |   58.1 | 0.6% | 0.555 | 0.0 |      162 | 0.0% |   0.0% |    - | 0.6% |   0.0309 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.8 | 20.0% | 0.689 | 0.4 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 33.3% | 0.755 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   18 |   96.5 | 27.8% | 0.688 | 0.4 |       15 | 0.0% |   0.0% |    - | 16.7% |   0.2000 |
|      ALL |   29 |   69.2 | 27.6% | 0.702 | 0.4 |       25 | 0.0% |   0.0% |    - | 18.2% |   0.1200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.8 | 0.0% | 0.002 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 0.0% | 0.016 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   96.5 | 0.0% | 0.013 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   29 |   69.2 | 0.0% | 0.012 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.8 | 0.0% | 0.547 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 0.0% | 0.523 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   96.5 | 0.0% | 0.549 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   69.2 | 0.0% | 0.543 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available