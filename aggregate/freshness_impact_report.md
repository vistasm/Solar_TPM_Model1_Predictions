# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-22 UTC
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
|    FRESH |   24 |   14.1 | 33.3% | 0.705 | 0.5 |       23 | 25.0% |  20.0% | 0.6× | 46.2% |   0.4348 |
|       OK |   16 |   34.6 | 37.5% | 0.700 | 0.8 |       15 | 16.7% |  33.3% | 0.8× | 41.7% |   0.2000 |
| DEGRADED |   34 |  106.8 | 38.2% | 0.698 | 0.4 |       32 | 0.0% |   0.0% |    - | 42.9% |   0.1250 |
|      ALL |   74 |   61.1 | 36.5% | 0.701 | 0.5 |       70 | 11.5% |  17.6% | 0.5× | 43.4% |   0.2429 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.1304 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
| DEGRADED |   34 |  106.8 | 0.0% | 0.004 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   74 |   61.1 | 0.0% | 0.013 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0857 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  106.8 | 0.0% | 0.472 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
|      ALL |   74 |   61.1 | 0.0% | 0.529 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0429 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 70.0% | 0.813 | 1.1 |        9 | 14.3% |  33.3% | 0.4× | 100.0% |   0.3333 |
|       OK |    7 |   31.7 | 28.6% | 0.648 | 0.9 |        6 | 50.0% | 100.0% | 3.0× | 20.0% |   0.1667 |
| DEGRADED |   14 |   93.4 | 35.7% | 0.731 | 0.4 |       12 | 0.0% |   0.0% |    - | 44.4% |   0.2500 |
|      ALL |   31 |   53.5 | 45.2% | 0.739 | 0.7 |       27 | 15.4% |  28.6% | 0.6× | 55.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.054 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   31.7 | 0.0% | 0.010 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |   14 |   93.4 | 0.0% | 0.002 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   53.5 | 0.0% | 0.021 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   12.9 | 0.0% | 0.678 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    7 |   31.7 | 0.0% | 0.582 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   93.4 | 0.0% | 0.536 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   53.5 | 0.0% | 0.592 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available