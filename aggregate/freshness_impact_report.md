# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-25 UTC
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
|       OK |   16 |   34.6 | 37.5% | 0.700 | 0.8 |       16 | 16.7% |  33.3% | 0.9× | 38.5% |   0.1875 |
| DEGRADED |   37 |  101.6 | 40.5% | 0.706 | 0.4 |       33 | 0.0% |   0.0% |    - | 41.4% |   0.1212 |
|      ALL |   77 |   60.4 | 37.7% | 0.704 | 0.5 |       73 | 11.5% |  17.6% | 0.5× | 41.1% |   0.2329 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
| DEGRADED |   37 |  101.6 | 0.0% | 0.004 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0606 |
|      ALL |   77 |   60.4 | 0.0% | 0.012 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0822 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   37 |  101.6 | 0.0% | 0.480 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0303 |
|      ALL |   77 |   60.4 | 0.0% | 0.531 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0411 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.8 | 66.7% | 0.805 | 1.1 |        9 | 16.7% |  33.3% | 0.5× | 83.3% |   0.3333 |
|       OK |    7 |   31.7 | 28.6% | 0.648 | 0.9 |        7 | 50.0% | 100.0% | 3.5× | 16.7% |   0.1429 |
| DEGRADED |   15 |   53.0 | 40.0% | 0.730 | 0.4 |       11 | 0.0% |   0.0% |    - | 33.3% |   0.1818 |
|      ALL |   31 |   36.8 | 45.2% | 0.733 | 0.7 |       27 | 18.2% |  33.3% | 0.8× | 42.9% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.8 | 0.0% | 0.058 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   31.7 | 0.0% | 0.010 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
| DEGRADED |   15 |   53.0 | 0.0% | 0.002 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   36.8 | 0.0% | 0.020 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.8 | 0.0% | 0.673 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   31.7 | 0.0% | 0.582 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   53.0 | 0.0% | 0.555 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.8 | 0.0% | 0.596 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available