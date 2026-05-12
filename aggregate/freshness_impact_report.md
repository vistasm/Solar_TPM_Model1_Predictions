# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-12 UTC
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
|       OK |   14 |   34.6 | 42.9% | 0.743 | 0.9 |       12 | 20.0% |  33.3% | 0.8× | 44.4% |   0.2500 |
| DEGRADED |   29 |  114.7 | 37.9% | 0.684 | 0.4 |       28 | 0.0% |   0.0% |    - | 44.0% |   0.1071 |
|      ALL |   64 |   64.2 | 37.5% | 0.708 | 0.5 |       60 | 13.6% |  20.0% | 0.6× | 42.2% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.031 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1500 |
|       OK |   14 |   34.6 | 0.0% | 0.010 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
| DEGRADED |   29 |  114.7 | 0.0% | 0.005 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |
|      ALL |   64 |   64.2 | 0.0% | 0.015 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.605 | 0.0 |       20 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |   14 |   34.6 | 0.0% | 0.556 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   29 |  114.7 | 0.0% | 0.457 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |
|      ALL |   64 |   64.2 | 0.0% | 0.527 | 0.0 |       60 |    - |   0.0% |    - | 0.0% |   0.0500 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 85.7% | 0.899 | 1.3 |        6 | 20.0% |  50.0% | 0.6× | 100.0% |   0.3333 |
|       OK |    5 |   30.5 | 40.0% | 0.746 | 1.2 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   19 |  146.0 | 21.1% | 0.639 | 0.2 |       18 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|      ALL |   31 |   97.3 | 38.7% | 0.715 | 0.6 |       27 | 20.0% |  40.0% | 1.1× | 36.4% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.077 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   30.5 | 0.0% | 0.014 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |   19 |  146.0 | 0.0% | 0.005 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   97.3 | 0.0% | 0.023 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.740 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   30.5 | 0.0% | 0.608 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  146.0 | 0.0% | 0.446 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   97.3 | 0.0% | 0.538 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available