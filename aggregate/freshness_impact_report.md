# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (44.4%) is 44.4% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.3%) is 3.0× the overall rate (1.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.2%) is 3.0× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 41.3% | 0.736 | 0.8 |       45 | 44.4% |  42.1% | 1.1× | 38.5% |   0.4222 |
|       OK |   26 |   32.2 | 42.3% | 0.729 | 0.7 |       24 | 22.2% |  40.0% | 1.1× | 36.8% |   0.2083 |
| DEGRADED |   66 |   94.2 | 36.4% | 0.678 | 0.4 |       65 | 0.0% |   0.0% |    - | 43.6% |   0.1538 |
|      ALL |  138 |   55.6 | 39.1% | 0.707 | 0.6 |      134 | 19.6% |  29.4% | 0.8× | 41.0% |   0.2537 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 4.3% | 0.050 | 0.0 |       45 | 50.0% |  12.5% | 2.8× | 2.7% |   0.1778 |
|       OK |   26 |   32.2 | 0.0% | 0.014 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
| DEGRADED |   66 |   94.2 | 0.0% | 0.013 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0615 |
|      ALL |  138 |   55.6 | 1.5% | 0.025 | 0.0 |      134 | 50.0% |   7.7% | 5.2× | 0.8% |   0.0970 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 2.2% | 0.645 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.4% |   0.0889 |
|       OK |   26 |   32.2 | 0.0% | 0.565 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   66 |   94.2 | 0.0% | 0.493 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  138 |   55.6 | 0.7% | 0.557 | 0.0 |      134 | 0.0% |   0.0% |    - | 0.8% |   0.0373 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 64.3% | 0.839 | 1.6 |       13 | 75.0% |  85.7% | 1.4× | 33.3% |   0.5385 |
|       OK |    5 |   20.4 | 60.0% | 0.832 | 0.8 |        3 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
| DEGRADED |   12 |   96.2 | 33.3% | 0.617 | 0.4 |       11 | 0.0% |   0.0% |    - | 40.0% |   0.0909 |
|      ALL |   31 |   45.7 | 51.6% | 0.752 | 1.0 |       27 | 53.8% |  70.0% | 1.4× | 35.3% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 14.3% | 0.114 | 0.1 |       13 | 50.0% |  25.0% | 1.6× | 11.1% |   0.3077 |
|       OK |    5 |   20.4 | 0.0% | 0.030 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   96.2 | 0.0% | 0.056 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.7 | 6.5% | 0.078 | 0.1 |       27 | 50.0% |  25.0% | 3.4× | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 7.1% | 0.747 | 0.1 |       13 | 0.0% |   0.0% |    - | 8.3% |   0.0769 |
|       OK |    5 |   20.4 | 0.0% | 0.550 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   96.2 | 0.0% | 0.530 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   45.7 | 3.2% | 0.631 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available