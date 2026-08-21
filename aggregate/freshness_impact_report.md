# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-21 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.0%) is 3.3× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.3× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 38.0% | 0.728 | 0.8 |       50 | 42.1% |  42.1% | 1.1× | 35.5% |   0.3800 |
|       OK |   32 |   32.3 | 40.6% | 0.734 | 0.6 |       31 | 15.4% |  40.0% | 0.9× | 42.3% |   0.1613 |
| DEGRADED |   81 |   96.4 | 33.3% | 0.678 | 0.4 |       78 | 0.0% |   0.0% |    - | 37.9% |   0.1538 |
|      ALL |  163 |   58.4 | 36.2% | 0.704 | 0.6 |      159 | 17.5% |  27.8% | 0.8× | 38.2% |   0.2264 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 4.0% | 0.046 | 0.0 |       50 | 50.0% |  12.5% | 3.1× | 2.4% |   0.1600 |
|       OK |   32 |   32.3 | 0.0% | 0.014 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.0323 |
| DEGRADED |   81 |   96.4 | 0.0% | 0.013 | 0.0 |       78 |    - |   0.0% |    - | 0.0% |   0.0513 |
|      ALL |  163 |   58.4 | 1.2% | 0.023 | 0.0 |      159 | 50.0% |   7.7% | 6.1× | 0.7% |   0.0818 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   50 |   13.5 | 2.0% | 0.635 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.2% |   0.0800 |
|       OK |   32 |   32.3 | 0.0% | 0.557 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   81 |   96.4 | 0.0% | 0.502 | 0.0 |       78 |    - |   0.0% |    - | 0.0% |   0.0128 |
|      ALL |  163 |   58.4 | 0.6% | 0.554 | 0.0 |      159 | 0.0% |   0.0% |    - | 0.7% |   0.0314 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   15.5 | 20.0% | 0.685 | 0.2 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
|       OK |    8 |   27.8 | 50.0% | 0.800 | 0.5 |        7 | 0.0% |      - |    - | 57.1% |   0.0000 |
| DEGRADED |   16 |  101.6 | 18.8% | 0.672 | 0.3 |       13 | 0.0% |   0.0% |    - | 9.1% |   0.1538 |
|      ALL |   29 |   66.4 | 27.6% | 0.710 | 0.3 |       25 | 0.0% |   0.0% |    - | 26.1% |   0.0800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   15.5 | 0.0% | 0.005 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   27.8 | 0.0% | 0.029 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  101.6 | 0.0% | 0.013 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.4 | 0.0% | 0.016 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   15.5 | 0.0% | 0.541 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   27.8 | 0.0% | 0.526 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  101.6 | 0.0% | 0.544 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.4 | 0.0% | 0.538 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available