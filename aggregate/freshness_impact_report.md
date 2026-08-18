# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.0%) is 3.2× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 38.0% | 0.728 | 0.8 |       49 | 42.1% |  42.1% | 1.1× | 36.7% |   0.3878 |
|       OK |   32 |   32.3 | 40.6% | 0.734 | 0.6 |       30 | 15.4% |  40.0% | 0.9× | 44.0% |   0.1667 |
| DEGRADED |   78 |   99.3 | 32.0% | 0.670 | 0.3 |       78 | 0.0% |   0.0% |    - | 37.9% |   0.1538 |
|      ALL |  160 |   59.1 | 35.6% | 0.701 | 0.5 |      157 | 17.5% |  27.8% | 0.8× | 38.8% |   0.2293 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 4.0% | 0.046 | 0.0 |       49 | 50.0% |  12.5% | 3.1× | 2.4% |   0.1633 |
|       OK |   32 |   32.3 | 0.0% | 0.014 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0333 |
| DEGRADED |   78 |   99.3 | 0.0% | 0.011 | 0.0 |       78 |    - |   0.0% |    - | 0.0% |   0.0513 |
|      ALL |  160 |   59.1 | 1.2% | 0.023 | 0.0 |      157 | 50.0% |   7.7% | 6.0× | 0.7% |   0.0828 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 2.0% | 0.635 | 0.0 |       49 | 0.0% |   0.0% |    - | 2.2% |   0.0816 |
|       OK |   32 |   32.3 | 0.0% | 0.557 | 0.0 |       30 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   78 |   99.3 | 0.0% | 0.499 | 0.0 |       78 |    - |   0.0% |    - | 0.0% |   0.0128 |
|      ALL |  160 |   59.1 | 0.6% | 0.553 | 0.0 |      157 | 0.0% |   0.0% |    - | 0.7% |   0.0318 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.1 | 33.3% | 0.706 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
|       OK |    8 |   27.8 | 50.0% | 0.800 | 0.5 |        6 | 0.0% |      - |    - | 66.7% |   0.0000 |
| DEGRADED |   15 |  121.0 | 13.3% | 0.613 | 0.1 |       15 | 0.0% |   0.0% |    - | 15.4% |   0.1333 |
|      ALL |   29 |   73.2 | 27.6% | 0.684 | 0.3 |       26 | 0.0% |   0.0% |    - | 33.3% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.1 | 0.0% | 0.005 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   27.8 | 0.0% | 0.029 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  121.0 | 0.0% | 0.003 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   73.2 | 0.0% | 0.010 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.1 | 0.0% | 0.523 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   27.8 | 0.0% | 0.526 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |  121.0 | 0.0% | 0.509 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   73.2 | 0.0% | 0.516 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available