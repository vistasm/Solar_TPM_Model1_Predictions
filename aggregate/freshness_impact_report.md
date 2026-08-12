# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-12 UTC
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
🟡 **X+**: FRESH alert rate (2.0%) is 3.1× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 38.8% | 0.727 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   30 |   32.4 | 43.3% | 0.740 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   76 |   99.9 | 32.9% | 0.670 | 0.4 |       74 | 0.0% |   0.0% |    - | 40.3% |   0.1622 |
|      ALL |  155 |   59.5 | 36.8% | 0.702 | 0.6 |      151 | 17.9% |  27.8% | 0.8× | 40.0% |   0.2384 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 4.1% | 0.047 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   30 |   32.4 | 0.0% | 0.013 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   76 |   99.9 | 0.0% | 0.012 | 0.0 |       74 |    - |   0.0% |    - | 0.0% |   0.0541 |
|      ALL |  155 |   59.5 | 1.3% | 0.023 | 0.0 |      151 | 50.0% |   7.7% | 5.8× | 0.7% |   0.0861 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 2.0% | 0.637 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   30 |   32.4 | 0.0% | 0.556 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   76 |   99.9 | 0.0% | 0.498 | 0.0 |       74 |    - |   0.0% |    - | 0.0% |   0.0135 |
|      ALL |  155 |   59.5 | 0.7% | 0.553 | 0.0 |      151 | 0.0% |   0.0% |    - | 0.7% |   0.0331 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.0 | 33.3% | 0.690 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
|       OK |    7 |   29.8 | 57.1% | 0.821 | 0.6 |        6 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   17 |  110.3 | 11.8% | 0.560 | 0.1 |       15 | 0.0% |   0.0% |    - | 15.4% |   0.1333 |
|      ALL |   30 |   72.7 | 26.7% | 0.647 | 0.3 |       26 | 0.0% |   0.0% |    - | 29.2% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.0 | 0.0% | 0.005 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   29.8 | 0.0% | 0.026 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  110.3 | 0.0% | 0.002 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   72.7 | 0.0% | 0.009 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   16.0 | 0.0% | 0.525 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   29.8 | 0.0% | 0.510 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  110.3 | 0.0% | 0.481 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   72.7 | 0.0% | 0.497 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available