# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (22.2%) is 22.2% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   14.3 | 31.0% | 0.706 | 0.5 |       27 | 22.2% |  18.2% | 0.6× | 43.8% |   0.4074 |
|       OK |   19 |   36.0 | 42.1% | 0.721 | 0.7 |       17 | 14.3% |  33.3% | 0.8× | 42.9% |   0.1765 |
| DEGRADED |   43 |  103.1 | 39.5% | 0.707 | 0.4 |       43 | 0.0% |   0.0% |    - | 47.2% |   0.1628 |
|      ALL |   91 |   60.8 | 37.4% | 0.710 | 0.5 |       87 | 9.1% |  14.3% | 0.4× | 45.5% |   0.2414 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   14.3 | 0.0% | 0.024 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |
|       OK |   19 |   36.0 | 0.0% | 0.011 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.004 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |   91 |   60.8 | 0.0% | 0.012 | 0.0 |       87 |    - |   0.0% |    - | 0.0% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   14.3 | 0.0% | 0.605 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |   19 |   36.0 | 0.0% | 0.567 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.493 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |   91 |   60.8 | 0.0% | 0.544 | 0.0 |       87 |    - |   0.0% |    - | 0.0% |   0.0460 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.6 | 33.3% | 0.701 | 0.7 |        7 | 0.0% |   0.0% |    - | 60.0% |   0.2857 |
|       OK |    7 |   39.6 | 42.9% | 0.664 | 0.6 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   15 |   78.1 | 40.0% | 0.752 | 0.4 |       15 | 0.0% |   0.0% |    - | 54.5% |   0.2667 |
|      ALL |   31 |   51.0 | 38.7% | 0.717 | 0.5 |       27 | 0.0% |   0.0% |    - | 52.4% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.6 | 0.0% | 0.048 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    7 |   39.6 | 0.0% | 0.010 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.1 | 0.0% | 0.002 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   31 |   51.0 | 0.0% | 0.017 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.6 | 0.0% | 0.603 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    7 |   39.6 | 0.0% | 0.587 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.1 | 0.0% | 0.568 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.0 | 0.0% | 0.582 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available