# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-11 UTC
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
|       OK |   13 |   34.2 | 38.5% | 0.734 | 0.8 |       12 | 20.0% |  33.3% | 0.8× | 44.4% |   0.2500 |
| DEGRADED |   29 |  114.7 | 37.9% | 0.684 | 0.4 |       27 | 0.0% |   0.0% |    - | 45.8% |   0.1111 |
|      ALL |   63 |   64.6 | 36.5% | 0.706 | 0.5 |       59 | 13.6% |  20.0% | 0.5× | 43.2% |   0.2542 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.031 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|       OK |   13 |   34.2 | 0.0% | 0.010 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
| DEGRADED |   29 |  114.7 | 0.0% | 0.005 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   63 |   64.6 | 0.0% | 0.015 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0847 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.605 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |   13 |   34.2 | 0.0% | 0.553 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   29 |  114.7 | 0.0% | 0.457 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   63 |   64.6 | 0.0% | 0.526 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0508 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 85.7% | 0.899 | 1.3 |        6 | 20.0% |  50.0% | 0.6× | 100.0% |   0.3333 |
|       OK |    5 |   31.4 | 20.0% | 0.687 | 0.8 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   19 |  146.0 | 21.1% | 0.639 | 0.2 |       17 | 0.0% |   0.0% |    - | 26.7% |   0.1176 |
|      ALL |   31 |   97.5 | 35.5% | 0.705 | 0.6 |       27 | 20.0% |  40.0% | 1.1× | 36.4% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.077 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   31.4 | 0.0% | 0.012 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   19 |  146.0 | 0.0% | 0.005 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   97.5 | 0.0% | 0.023 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.740 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   31.4 | 0.0% | 0.557 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  146.0 | 0.0% | 0.446 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   97.5 | 0.0% | 0.530 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available