# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.1%) is 3.1× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.1× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 38.8% | 0.727 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   76 |   99.9 | 32.9% | 0.670 | 0.4 |       73 | 0.0% |   0.0% |    - | 41.0% |   0.1644 |
|      ALL |  154 |   59.7 | 36.4% | 0.700 | 0.6 |      150 | 17.9% |  27.8% | 0.7× | 40.4% |   0.2400 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 4.1% | 0.047 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   76 |   99.9 | 0.0% | 0.012 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0548 |
|      ALL |  154 |   59.7 | 1.3% | 0.023 | 0.0 |      150 | 50.0% |   7.7% | 5.8× | 0.7% |   0.0867 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 2.0% | 0.637 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   76 |   99.9 | 0.0% | 0.498 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0137 |
|      ALL |  154 |   59.7 | 0.7% | 0.553 | 0.0 |      150 | 0.0% |   0.0% |    - | 0.7% |   0.0333 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.0 | 33.3% | 0.690 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
|       OK |    7 |   24.7 | 42.9% | 0.778 | 0.4 |        7 | 0.0% |   0.0% |    - | 50.0% |   0.1429 |
| DEGRADED |   17 |  110.3 | 11.8% | 0.560 | 0.1 |       14 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
|      ALL |   30 |   71.5 | 23.3% | 0.637 | 0.2 |       26 | 0.0% |   0.0% |    - | 30.4% |   0.1154 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.0 | 0.0% | 0.005 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   24.7 | 0.0% | 0.027 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  110.3 | 0.0% | 0.002 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   71.5 | 0.0% | 0.009 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.0 | 0.0% | 0.525 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   24.7 | 0.0% | 0.498 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  110.3 | 0.0% | 0.481 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   71.5 | 0.0% | 0.494 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available