# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-07 UTC
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
|    FRESH |   29 |   14.3 | 31.0% | 0.706 | 0.5 |       26 | 25.0% |  18.2% | 0.6× | 40.0% |   0.4231 |
|       OK |   18 |   35.7 | 44.4% | 0.726 | 0.8 |       17 | 14.3% |  33.3% | 0.8× | 42.9% |   0.1765 |
| DEGRADED |   43 |  103.1 | 39.5% | 0.707 | 0.4 |       43 | 0.0% |   0.0% |    - | 47.2% |   0.1628 |
|      ALL |   90 |   61.0 | 37.8% | 0.711 | 0.5 |       86 | 9.4% |  14.3% | 0.4× | 44.6% |   0.2442 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   14.3 | 0.0% | 0.024 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |   18 |   35.7 | 0.0% | 0.008 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.004 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |   90 |   61.0 | 0.0% | 0.011 | 0.0 |       86 |    - |   0.0% |    - | 0.0% |   0.0930 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   29 |   14.3 | 0.0% | 0.605 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1154 |
|       OK |   18 |   35.7 | 0.0% | 0.564 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.493 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |   90 |   61.0 | 0.0% | 0.543 | 0.0 |       86 |    - |   0.0% |    - | 0.0% |   0.0465 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.6 | 33.3% | 0.701 | 0.7 |        6 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
|       OK |    6 |   39.6 | 50.0% | 0.670 | 0.7 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   16 |   74.1 | 37.5% | 0.736 | 0.4 |       16 | 0.0% |   0.0% |    - | 50.0% |   0.2500 |
|      ALL |   31 |   50.2 | 38.7% | 0.713 | 0.5 |       27 | 0.0% |   0.0% |    - | 47.6% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.6 | 0.0% | 0.048 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   39.6 | 0.0% | 0.003 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   74.1 | 0.0% | 0.002 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   50.2 | 0.0% | 0.015 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.6 | 0.0% | 0.603 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    6 |   39.6 | 0.0% | 0.581 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   74.1 | 0.0% | 0.565 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   50.2 | 0.0% | 0.579 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available