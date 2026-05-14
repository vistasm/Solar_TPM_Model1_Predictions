# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (33.3%) is 33.3% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 33.3% | 0.718 | 0.5 |       20 | 33.3% |  22.2% | 0.7× | 36.4% |   0.4500 |
|       OK |   14 |   34.6 | 42.9% | 0.743 | 0.9 |       13 | 20.0% |  33.3% | 0.9× | 40.0% |   0.2308 |
| DEGRADED |   31 |  112.2 | 38.7% | 0.693 | 0.4 |       29 | 0.0% |   0.0% |    - | 44.0% |   0.1379 |
|      ALL |   66 |   64.6 | 37.9% | 0.712 | 0.5 |       62 | 13.6% |  18.8% | 0.5× | 41.3% |   0.2581 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.031 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|       OK |   14 |   34.6 | 0.0% | 0.010 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
| DEGRADED |   31 |  112.2 | 0.0% | 0.005 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0690 |
|      ALL |   66 |   64.6 | 0.0% | 0.014 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0968 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.605 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |   14 |   34.6 | 0.0% | 0.556 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   31 |  112.2 | 0.0% | 0.465 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
|      ALL |   66 |   64.6 | 0.0% | 0.529 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0484 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 85.7% | 0.899 | 1.3 |        6 | 20.0% |  50.0% | 0.6× | 100.0% |   0.3333 |
|       OK |    5 |   30.5 | 40.0% | 0.746 | 1.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   19 |  145.5 | 26.3% | 0.667 | 0.3 |       17 | 0.0% |   0.0% |    - | 28.6% |   0.1765 |
|      ALL |   31 |   97.0 | 41.9% | 0.732 | 0.7 |       27 | 20.0% |  33.3% | 0.9× | 38.1% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.077 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   30.5 | 0.0% | 0.014 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   19 |  145.5 | 0.0% | 0.006 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |
|      ALL |   31 |   97.0 | 0.0% | 0.023 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.740 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   30.5 | 0.0% | 0.608 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  145.5 | 0.0% | 0.475 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   97.0 | 0.0% | 0.556 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available