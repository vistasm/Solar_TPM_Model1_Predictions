# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (37.0%) is 25.4% HIGHER than DEGRADED (11.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.0%) is 4.0× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.5%) is 4.0× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   66 |   13.4 | 42.4% | 0.730 | 0.7 |       65 | 37.0% |  45.5% | 1.1× | 39.5% |   0.3385 |
|       OK |   39 |   33.1 | 43.6% | 0.736 | 0.6 |       39 | 17.6% |  50.0% | 1.1× | 42.4% |   0.1538 |
| DEGRADED |  159 |   98.4 | 27.0% | 0.617 | 0.3 |      156 | 11.6% |  19.2% | 0.7× | 29.2% |   0.1667 |
|      ALL |  264 |   67.5 | 33.3% | 0.663 | 0.5 |      260 | 20.7% |  33.3% | 1.0× | 33.5% |   0.2077 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   66 |   13.4 | 3.0% | 0.036 | 0.0 |       65 | 50.0% |  11.1% | 3.6× | 1.8% |   0.1385 |
|       OK |   39 |   33.1 | 0.0% | 0.015 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
| DEGRADED |  159 |   98.4 | 0.0% | 0.012 | 0.0 |      156 |    - |   0.0% |    - | 0.0% |   0.0449 |
|      ALL |  264 |   67.5 | 0.8% | 0.018 | 0.0 |      260 | 50.0% |   5.9% | 7.7× | 0.4% |   0.0654 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   66 |   13.4 | 1.5% | 0.621 | 0.0 |       65 | 0.0% |   0.0% |    - | 1.6% |   0.0615 |
|       OK |   39 |   33.1 | 0.0% | 0.560 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  159 |   98.4 | 0.0% | 0.521 | 0.0 |      156 |    - |   0.0% |    - | 0.0% |   0.0064 |
|      ALL |  264 |   67.5 | 0.4% | 0.552 | 0.0 |      260 | 0.0% |   0.0% |    - | 0.4% |   0.0192 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   11.5 | 66.7% | 0.837 | 0.7 |        5 | 0.0% |   0.0% |    - | 75.0% |   0.2000 |
|       OK |    3 |   34.4 | 66.7% | 0.819 | 1.0 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   22 |   91.8 | 13.6% | 0.453 | 0.1 |       19 | 33.3% |  25.0% | 1.6× | 13.3% |   0.2105 |
|      ALL |   31 |   70.7 | 29.0% | 0.562 | 0.3 |       27 | 25.0% |  33.3% | 1.1× | 28.6% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   11.5 | 0.0% | 0.008 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.038 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |   91.8 | 0.0% | 0.000 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.7 | 0.0% | 0.006 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   11.5 | 0.0% | 0.572 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.596 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |   91.8 | 0.0% | 0.518 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   70.7 | 0.0% | 0.536 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available