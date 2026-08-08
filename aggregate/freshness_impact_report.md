# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 3.2× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.2× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   74 |   96.1 | 33.8% | 0.678 | 0.4 |       71 | 0.0% |   0.0% |    - | 42.4% |   0.1690 |
|      ALL |  151 |   57.6 | 37.1% | 0.706 | 0.6 |      148 | 17.9% |  27.8% | 0.7× | 41.1% |   0.2432 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   74 |   96.1 | 0.0% | 0.012 | 0.0 |       71 |    - |   0.0% |    - | 0.0% |   0.0563 |
|      ALL |  151 |   57.6 | 1.3% | 0.024 | 0.0 |      148 | 50.0% |   7.7% | 5.7× | 0.7% |   0.0878 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   74 |   96.1 | 0.0% | 0.499 | 0.0 |       71 |    - |   0.0% |    - | 0.0% |   0.0141 |
|      ALL |  151 |   57.6 | 0.7% | 0.554 | 0.0 |      148 | 0.0% |   0.0% |    - | 0.7% |   0.0338 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.1 | 25.0% | 0.709 | 0.2 |        8 | 0.0% |      - |    - | 25.0% |   0.0000 |
|       OK |    7 |   24.7 | 42.9% | 0.778 | 0.4 |        7 | 0.0% |   0.0% |    - | 50.0% |   0.1429 |
| DEGRADED |   15 |   92.9 | 13.3% | 0.582 | 0.1 |       12 | 0.0% |   0.0% |    - | 20.0% |   0.1667 |
|      ALL |   30 |   56.5 | 23.3% | 0.661 | 0.2 |       27 | 0.0% |   0.0% |    - | 29.2% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.1 | 0.0% | 0.007 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   24.7 | 0.0% | 0.027 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   92.9 | 0.0% | 0.003 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   56.5 | 0.0% | 0.009 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.1 | 0.0% | 0.531 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   24.7 | 0.0% | 0.498 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   92.9 | 0.0% | 0.481 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   56.5 | 0.0% | 0.498 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available