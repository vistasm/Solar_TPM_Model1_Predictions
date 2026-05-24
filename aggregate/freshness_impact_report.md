# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (25.0%) is 25.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 33.3% | 0.705 | 0.5 |       24 | 25.0% |  20.0% | 0.6× | 42.9% |   0.4167 |
|       OK |   16 |   34.6 | 37.5% | 0.700 | 0.8 |       15 | 16.7% |  33.3% | 0.8× | 41.7% |   0.2000 |
| DEGRADED |   36 |  102.6 | 38.9% | 0.702 | 0.4 |       33 | 0.0% |   0.0% |    - | 41.4% |   0.1212 |
|      ALL |   76 |   60.3 | 36.8% | 0.703 | 0.5 |       72 | 11.5% |  17.6% | 0.5× | 41.8% |   0.2361 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
| DEGRADED |   36 |  102.6 | 0.0% | 0.004 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0606 |
|      ALL |   76 |   60.3 | 0.0% | 0.013 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   36 |  102.6 | 0.0% | 0.476 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0303 |
|      ALL |   76 |   60.3 | 0.0% | 0.530 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 70.0% | 0.813 | 1.1 |       10 | 14.3% |  33.3% | 0.5× | 85.7% |   0.3000 |
|       OK |    7 |   31.7 | 28.6% | 0.648 | 0.9 |        6 | 50.0% | 100.0% | 3.0× | 20.0% |   0.1667 |
| DEGRADED |   14 |   52.0 | 35.7% | 0.722 | 0.4 |       11 | 0.0% |   0.0% |    - | 33.3% |   0.1818 |
|      ALL |   31 |   34.8 | 45.2% | 0.735 | 0.7 |       27 | 16.7% |  33.3% | 0.8× | 47.6% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.054 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    7 |   31.7 | 0.0% | 0.010 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |   14 |   52.0 | 0.0% | 0.002 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   34.8 | 0.0% | 0.021 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.678 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    7 |   31.7 | 0.0% | 0.582 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   52.0 | 0.0% | 0.550 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.8 | 0.0% | 0.599 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available