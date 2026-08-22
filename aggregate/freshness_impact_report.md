# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 3.2× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   13.7 | 39.2% | 0.731 | 0.8 |       50 | 42.1% |  42.1% | 1.1× | 35.5% |   0.3800 |
|       OK |   32 |   32.3 | 40.6% | 0.734 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   81 |   96.4 | 33.3% | 0.678 | 0.4 |       78 | 0.0% |   0.0% |    - | 37.9% |   0.1538 |
|      ALL |  164 |   58.1 | 36.6% | 0.706 | 0.6 |      160 | 17.5% |  27.8% | 0.8× | 37.9% |   0.2250 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   13.7 | 3.9% | 0.045 | 0.0 |       50 | 50.0% |  12.5% | 3.1× | 2.4% |   0.1600 |
|       OK |   32 |   32.3 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   81 |   96.4 | 0.0% | 0.013 | 0.0 |       78 |    - |   0.0% |    - | 0.0% |   0.0513 |
|      ALL |  164 |   58.1 | 1.2% | 0.023 | 0.0 |      160 | 50.0% |   7.7% | 6.2× | 0.7% |   0.0813 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   13.7 | 2.0% | 0.635 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.2% |   0.0800 |
|       OK |   32 |   32.3 | 0.0% | 0.557 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   81 |   96.4 | 0.0% | 0.502 | 0.0 |       78 |    - |   0.0% |    - | 0.0% |   0.0128 |
|      ALL |  164 |   58.1 | 0.6% | 0.554 | 0.0 |      160 | 0.0% |   0.0% |    - | 0.7% |   0.0312 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.2 | 33.3% | 0.720 | 0.5 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
|       OK |    7 |   30.0 | 42.9% | 0.782 | 0.4 |        7 | 0.0% |      - |    - | 42.9% |   0.0000 |
| DEGRADED |   16 |  101.6 | 18.8% | 0.672 | 0.3 |       13 | 0.0% |   0.0% |    - | 9.1% |   0.1538 |
|      ALL |   29 |   66.7 | 27.6% | 0.709 | 0.4 |       25 | 0.0% |   0.0% |    - | 21.7% |   0.0800 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.2 | 0.0% | 0.005 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   30.0 | 0.0% | 0.015 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  101.6 | 0.0% | 0.013 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.7 | 0.0% | 0.012 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.2 | 0.0% | 0.555 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   30.0 | 0.0% | 0.517 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  101.6 | 0.0% | 0.544 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.7 | 0.0% | 0.539 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available