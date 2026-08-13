# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.1%) is 3.2× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 38.8% | 0.727 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   30 |   32.4 | 43.3% | 0.740 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   77 |   99.4 | 32.5% | 0.671 | 0.3 |       75 | 0.0% |   0.0% |    - | 39.7% |   0.1600 |
|      ALL |  156 |   59.6 | 36.5% | 0.702 | 0.5 |      152 | 17.9% |  27.8% | 0.8× | 39.7% |   0.2368 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 4.1% | 0.047 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   30 |   32.4 | 0.0% | 0.013 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   77 |   99.4 | 0.0% | 0.012 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0533 |
|      ALL |  156 |   59.6 | 1.3% | 0.023 | 0.0 |      152 | 50.0% |   7.7% | 5.8× | 0.7% |   0.0855 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 2.0% | 0.637 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   30 |   32.4 | 0.0% | 0.556 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   77 |   99.4 | 0.0% | 0.499 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0133 |
|      ALL |  156 |   59.6 | 0.6% | 0.553 | 0.0 |      152 | 0.0% |   0.0% |    - | 0.7% |   0.0329 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.9 | 40.0% | 0.695 | 0.4 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
|       OK |    7 |   29.8 | 57.1% | 0.821 | 0.6 |        6 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   18 |  107.8 | 11.1% | 0.570 | 0.1 |       16 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   30 |   74.1 | 26.7% | 0.650 | 0.3 |       26 | 0.0% |   0.0% |    - | 29.2% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.9 | 0.0% | 0.005 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   29.8 | 0.0% | 0.026 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  107.8 | 0.0% | 0.002 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   74.1 | 0.0% | 0.008 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.9 | 0.0% | 0.518 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   29.8 | 0.0% | 0.510 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  107.8 | 0.0% | 0.485 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   74.1 | 0.0% | 0.496 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available