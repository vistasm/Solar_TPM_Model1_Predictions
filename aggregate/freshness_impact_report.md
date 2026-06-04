# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-04 UTC
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
|    FRESH |   27 |   14.2 | 33.3% | 0.706 | 0.5 |       25 | 25.0% |  20.0% | 0.6× | 40.0% |   0.4000 |
|       OK |   17 |   35.4 | 41.2% | 0.715 | 0.8 |       17 | 14.3% |  33.3% | 0.8× | 42.9% |   0.1765 |
| DEGRADED |   43 |  103.1 | 39.5% | 0.707 | 0.4 |       41 | 0.0% |   0.0% |    - | 47.2% |   0.1220 |
|      ALL |   87 |   62.3 | 37.9% | 0.708 | 0.5 |       83 | 9.4% |  16.7% | 0.4× | 44.6% |   0.2169 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   14.2 | 0.0% | 0.025 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1200 |
|       OK |   17 |   35.4 | 0.0% | 0.009 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.004 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.0488 |
|      ALL |   87 |   62.3 | 0.0% | 0.011 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0723 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   27 |   14.2 | 0.0% | 0.603 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|       OK |   17 |   35.4 | 0.0% | 0.553 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.493 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.0244 |
|      ALL |   87 |   62.3 | 0.0% | 0.539 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0361 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.4 | 42.9% | 0.700 | 0.9 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
|       OK |    6 |   37.2 | 33.3% | 0.637 | 0.5 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   18 |   73.0 | 33.3% | 0.709 | 0.3 |       16 | 0.0% |   0.0% |    - | 46.2% |   0.1875 |
|      ALL |   31 |   52.9 | 35.5% | 0.693 | 0.5 |       27 | 0.0% |   0.0% |    - | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.4 | 0.0% | 0.060 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.003 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   73.0 | 0.0% | 0.001 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   52.9 | 0.0% | 0.015 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.4 | 0.0% | 0.596 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.545 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   73.0 | 0.0% | 0.562 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.9 | 0.0% | 0.566 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available