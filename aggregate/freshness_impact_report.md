# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.0%) is 3.2× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 38.0% | 0.728 | 0.8 |       49 | 42.1% |  42.1% | 1.1× | 36.7% |   0.3878 |
|       OK |   31 |   32.9 | 41.9% | 0.734 | 0.7 |       30 | 15.4% |  40.0% | 0.9× | 44.0% |   0.1667 |
| DEGRADED |   78 |   99.3 | 32.0% | 0.670 | 0.3 |       77 | 0.0% |   0.0% |    - | 38.5% |   0.1558 |
|      ALL |  159 |   59.4 | 35.9% | 0.701 | 0.5 |      156 | 17.5% |  27.8% | 0.8× | 39.2% |   0.2308 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 4.0% | 0.046 | 0.0 |       49 | 50.0% |  12.5% | 3.1× | 2.4% |   0.1633 |
|       OK |   31 |   32.9 | 0.0% | 0.013 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0333 |
| DEGRADED |   78 |   99.3 | 0.0% | 0.011 | 0.0 |       77 |    - |   0.0% |    - | 0.0% |   0.0519 |
|      ALL |  159 |   59.4 | 1.3% | 0.023 | 0.0 |      156 | 50.0% |   7.7% | 6.0× | 0.7% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 2.0% | 0.635 | 0.0 |       49 | 0.0% |   0.0% |    - | 2.2% |   0.0816 |
|       OK |   31 |   32.9 | 0.0% | 0.556 | 0.0 |       30 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   78 |   99.3 | 0.0% | 0.499 | 0.0 |       77 |    - |   0.0% |    - | 0.0% |   0.0130 |
|      ALL |  159 |   59.4 | 0.6% | 0.553 | 0.0 |      156 | 0.0% |   0.0% |    - | 0.7% |   0.0321 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.1 | 33.3% | 0.706 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
|       OK |    7 |   29.9 | 57.1% | 0.809 | 0.6 |        6 | 0.0% |      - |    - | 66.7% |   0.0000 |
| DEGRADED |   16 |  119.0 | 12.5% | 0.609 | 0.1 |       15 | 0.0% |   0.0% |    - | 15.4% |   0.1333 |
|      ALL |   29 |   75.8 | 27.6% | 0.677 | 0.3 |       26 | 0.0% |   0.0% |    - | 33.3% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.1 | 0.0% | 0.005 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   29.9 | 0.0% | 0.026 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  119.0 | 0.0% | 0.003 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.8 | 0.0% | 0.009 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.1 | 0.0% | 0.523 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   29.9 | 0.0% | 0.519 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  119.0 | 0.0% | 0.501 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   75.8 | 0.0% | 0.510 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available