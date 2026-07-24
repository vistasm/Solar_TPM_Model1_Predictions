# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (47.1%) is 47.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.3%) is 3.0× the overall rate (1.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.2%) is 3.0× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 41.3% | 0.736 | 0.8 |       44 | 47.1% |  42.1% | 1.1× | 36.0% |   0.4318 |
|       OK |   26 |   32.2 | 42.3% | 0.729 | 0.7 |       24 | 22.2% |  40.0% | 1.1× | 36.8% |   0.2083 |
| DEGRADED |   65 |   95.1 | 36.9% | 0.679 | 0.4 |       65 | 0.0% |   0.0% |    - | 43.6% |   0.1538 |
|      ALL |  137 |   55.8 | 39.4% | 0.708 | 0.6 |      133 | 20.0% |  29.4% | 0.8× | 40.4% |   0.2556 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 4.3% | 0.050 | 0.0 |       44 | 50.0% |  12.5% | 2.8× | 2.8% |   0.1818 |
|       OK |   26 |   32.2 | 0.0% | 0.014 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
| DEGRADED |   65 |   95.1 | 0.0% | 0.013 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0615 |
|      ALL |  137 |   55.8 | 1.5% | 0.026 | 0.0 |      133 | 50.0% |   7.7% | 5.1× | 0.8% |   0.0977 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 2.2% | 0.645 | 0.0 |       44 | 0.0% |   0.0% |    - | 2.5% |   0.0909 |
|       OK |   26 |   32.2 | 0.0% | 0.565 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |   95.1 | 0.0% | 0.492 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  137 |   55.8 | 0.7% | 0.557 | 0.0 |      133 | 0.0% |   0.0% |    - | 0.8% |   0.0376 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 64.3% | 0.839 | 1.6 |       12 | 85.7% |  85.7% | 1.5× | 20.0% |   0.5833 |
|       OK |    5 |   20.4 | 60.0% | 0.832 | 0.8 |        3 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
| DEGRADED |   12 |   97.8 | 33.3% | 0.628 | 0.4 |       12 | 0.0% |   0.0% |    - | 36.4% |   0.0833 |
|      ALL |   31 |   46.3 | 51.6% | 0.756 | 1.0 |       27 | 58.3% |  70.0% | 1.6× | 29.4% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 14.3% | 0.114 | 0.1 |       12 | 50.0% |  25.0% | 1.5× | 12.5% |   0.3333 |
|       OK |    5 |   20.4 | 0.0% | 0.030 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   97.8 | 0.0% | 0.056 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.3 | 6.5% | 0.078 | 0.1 |       27 | 50.0% |  25.0% | 3.4× | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 7.1% | 0.747 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    5 |   20.4 | 0.0% | 0.550 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   97.8 | 0.0% | 0.531 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.3 | 3.2% | 0.632 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available