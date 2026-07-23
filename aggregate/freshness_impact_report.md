# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-23 UTC
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
🟡 **X+**: FRESH alert rate (2.2%) is 2.9× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 41.3% | 0.736 | 0.8 |       44 | 47.1% |  42.1% | 1.1× | 36.0% |   0.4318 |
|       OK |   25 |   32.9 | 40.0% | 0.721 | 0.7 |       24 | 22.2% |  40.0% | 1.1× | 36.8% |   0.2083 |
| DEGRADED |   65 |   95.1 | 36.9% | 0.679 | 0.4 |       64 | 0.0% |   0.0% |    - | 42.6% |   0.1562 |
|      ALL |  136 |   56.1 | 39.0% | 0.706 | 0.6 |      132 | 20.4% |  29.4% | 0.8× | 39.8% |   0.2576 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 4.3% | 0.050 | 0.0 |       44 | 50.0% |  12.5% | 2.8× | 2.8% |   0.1818 |
|       OK |   25 |   32.9 | 0.0% | 0.014 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0417 |
| DEGRADED |   65 |   95.1 | 0.0% | 0.013 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |  136 |   56.1 | 1.5% | 0.026 | 0.0 |      132 | 50.0% |   7.7% | 5.1× | 0.8% |   0.0985 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   46 |   13.5 | 2.2% | 0.645 | 0.0 |       44 | 0.0% |   0.0% |    - | 2.5% |   0.0909 |
|       OK |   25 |   32.9 | 0.0% | 0.568 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |   95.1 | 0.0% | 0.492 | 0.0 |       64 |    - |   0.0% |    - | 0.0% |   0.0156 |
|      ALL |  136 |   56.1 | 0.7% | 0.558 | 0.0 |      132 | 0.0% |   0.0% |    - | 0.8% |   0.0379 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 64.3% | 0.839 | 1.6 |       12 | 85.7% |  85.7% | 1.5× | 20.0% |   0.5833 |
|       OK |    4 |   21.9 | 50.0% | 0.804 | 0.8 |        3 | 100.0% |  50.0% | 1.5× | 0.0% |   0.6667 |
| DEGRADED |   13 |   93.0 | 30.8% | 0.638 | 0.4 |       12 | 0.0% |   0.0% |    - | 27.3% |   0.0833 |
|      ALL |   31 |   46.9 | 48.4% | 0.750 | 1.0 |       27 | 63.6% |  70.0% | 1.7× | 23.5% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 14.3% | 0.114 | 0.1 |       12 | 50.0% |  25.0% | 1.5× | 12.5% |   0.3333 |
|       OK |    4 |   21.9 | 0.0% | 0.035 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   93.0 | 0.0% | 0.051 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.9 | 6.5% | 0.078 | 0.1 |       27 | 50.0% |  25.0% | 3.4× | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   11.4 | 7.1% | 0.747 | 0.1 |       12 | 0.0% |   0.0% |    - | 9.1% |   0.0833 |
|       OK |    4 |   21.9 | 0.0% | 0.568 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   93.0 | 0.0% | 0.541 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.9 | 3.2% | 0.637 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available