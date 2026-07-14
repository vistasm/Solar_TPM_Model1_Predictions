# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (47.1%) is 47.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.5%) is 2.9× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.3%) is 2.9× the overall rate (0.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   13.5 | 38.6% | 0.731 | 0.8 |       42 | 47.1% |  42.1% | 1.0× | 39.1% |   0.4524 |
|       OK |   24 |   33.7 | 37.5% | 0.713 | 0.7 |       22 | 22.2% |  50.0% | 1.2× | 38.9% |   0.1818 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  127 |   56.0 | 38.6% | 0.714 | 0.6 |      123 | 20.4% |  30.3% | 0.8× | 43.3% |   0.2683 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   13.5 | 4.5% | 0.052 | 0.1 |       42 | 50.0% |  12.5% | 2.6× | 2.9% |   0.1905 |
|       OK |   24 |   33.7 | 0.0% | 0.009 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  127 |   56.0 | 1.6% | 0.026 | 0.0 |      123 | 50.0% |   7.7% | 4.7× | 0.9% |   0.1057 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   13.5 | 2.3% | 0.651 | 0.0 |       42 | 0.0% |   0.0% |    - | 2.6% |   0.0952 |
|       OK |   24 |   33.7 | 0.0% | 0.567 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  127 |   56.0 | 0.8% | 0.566 | 0.0 |      123 | 0.0% |   0.0% |    - | 0.9% |   0.0406 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.2 | 53.8% | 0.791 | 1.6 |       11 | 85.7% |  85.7% | 1.4× | 25.0% |   0.6364 |
|       OK |    3 |   25.1 | 33.3% | 0.764 | 0.7 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   15 |   81.1 | 33.3% | 0.672 | 0.4 |       15 | 0.0% |   0.0% |    - | 41.7% |   0.2000 |
|      ALL |   31 |   46.4 | 41.9% | 0.731 | 0.9 |       27 | 53.8% |  63.6% | 1.3× | 37.5% |   0.4074 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.2 | 15.4% | 0.121 | 0.1 |       11 | 50.0% |  25.0% | 1.4× | 14.3% |   0.3636 |
|       OK |    3 |   25.1 | 0.0% | 0.004 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   81.1 | 0.0% | 0.045 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   46.4 | 6.5% | 0.073 | 0.1 |       27 | 50.0% |  20.0% | 2.7× | 4.5% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.2 | 7.7% | 0.751 | 0.1 |       11 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |    3 |   25.1 | 0.0% | 0.560 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   81.1 | 0.0% | 0.527 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 3.2% | 0.625 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available