# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-07 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 3.1× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.1× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   73 |   94.6 | 34.2% | 0.684 | 0.4 |       70 | 0.0% |   0.0% |    - | 43.1% |   0.1714 |
|      ALL |  150 |   56.6 | 37.3% | 0.709 | 0.6 |      147 | 17.9% |  27.8% | 0.7× | 41.4% |   0.2449 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   73 |   94.6 | 0.0% | 0.012 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0571 |
|      ALL |  150 |   56.6 | 1.3% | 0.024 | 0.0 |      147 | 50.0% |   7.7% | 5.7× | 0.8% |   0.0884 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   73 |   94.6 | 0.0% | 0.499 | 0.0 |       70 |    - |   0.0% |    - | 0.0% |   0.0143 |
|      ALL |  150 |   56.6 | 0.7% | 0.555 | 0.0 |      147 | 0.0% |   0.0% |    - | 0.7% |   0.0340 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.0 | 22.2% | 0.711 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    7 |   24.7 | 42.9% | 0.778 | 0.4 |        7 | 0.0% |   0.0% |    - | 50.0% |   0.1429 |
| DEGRADED |   14 |   84.9 | 14.3% | 0.605 | 0.1 |       11 | 0.0% |   0.0% |    - | 22.2% |   0.1818 |
|      ALL |   30 |   50.2 | 23.3% | 0.677 | 0.2 |       27 | 0.0% |   0.0% |    - | 30.4% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.0 | 0.0% | 0.006 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   24.7 | 0.0% | 0.027 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.9 | 0.0% | 0.003 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   50.2 | 0.0% | 0.009 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.0 | 0.0% | 0.545 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   24.7 | 0.0% | 0.498 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   84.9 | 0.0% | 0.481 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   50.2 | 0.0% | 0.504 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available