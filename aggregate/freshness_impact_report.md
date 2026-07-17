# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (47.1%) is 47.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.5%) is 3.0× the overall rate (1.5%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.3%) is 2.9× the overall rate (0.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   13.5 | 38.6% | 0.731 | 0.8 |       44 | 47.1% |  42.1% | 1.1× | 36.0% |   0.4318 |
|       OK |   24 |   33.7 | 37.5% | 0.713 | 0.7 |       23 | 22.2% |  40.0% | 1.0× | 38.9% |   0.2174 |
| DEGRADED |   62 |   94.2 | 37.1% | 0.686 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  130 |   55.7 | 37.7% | 0.706 | 0.6 |      126 | 20.4% |  29.4% | 0.8× | 42.4% |   0.2698 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   13.5 | 4.5% | 0.052 | 0.1 |       44 | 50.0% |  12.5% | 2.8× | 2.8% |   0.1818 |
|       OK |   24 |   33.7 | 0.0% | 0.009 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
| DEGRADED |   62 |   94.2 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  130 |   55.7 | 1.5% | 0.026 | 0.0 |      126 | 50.0% |   7.7% | 4.8× | 0.9% |   0.1032 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   44 |   13.5 | 2.3% | 0.651 | 0.0 |       44 | 0.0% |   0.0% |    - | 2.5% |   0.0909 |
|       OK |   24 |   33.7 | 0.0% | 0.567 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   62 |   94.2 | 0.0% | 0.499 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  130 |   55.7 | 0.8% | 0.563 | 0.0 |      126 | 0.0% |   0.0% |    - | 0.8% |   0.0397 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.7 | 58.3% | 0.839 | 1.8 |       12 | 85.7% |  85.7% | 1.5× | 20.0% |   0.5833 |
|       OK |    3 |   25.1 | 33.3% | 0.764 | 0.7 |        2 | 100.0% |  50.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   16 |   77.2 | 31.2% | 0.644 | 0.4 |       13 | 0.0% |   0.0% |    - | 50.0% |   0.2308 |
|      ALL |   31 |   46.4 | 41.9% | 0.731 | 0.9 |       27 | 53.8% |  58.3% | 1.2× | 40.0% |   0.4444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.7 | 16.7% | 0.132 | 0.2 |       12 | 50.0% |  25.0% | 1.5× | 12.5% |   0.3333 |
|       OK |    3 |   25.1 | 0.0% | 0.004 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   77.2 | 0.0% | 0.042 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   46.4 | 6.5% | 0.073 | 0.1 |       27 | 50.0% |  20.0% | 2.7× | 4.5% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   10.7 | 8.3% | 0.787 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    3 |   25.1 | 0.0% | 0.560 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   77.2 | 0.0% | 0.529 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 3.2% | 0.631 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available