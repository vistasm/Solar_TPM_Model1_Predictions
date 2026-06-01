# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-01 UTC
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
|    FRESH |   25 |   14.5 | 32.0% | 0.697 | 0.5 |       24 | 25.0% |  20.0% | 0.6× | 42.9% |   0.4167 |
|       OK |   17 |   35.4 | 41.2% | 0.715 | 0.8 |       16 | 16.7% |  33.3% | 0.9× | 38.5% |   0.1875 |
| DEGRADED |   42 |  103.3 | 40.5% | 0.710 | 0.4 |       40 | 0.0% |   0.0% |    - | 47.2% |   0.1000 |
|      ALL |   84 |   63.1 | 38.1% | 0.707 | 0.5 |       80 | 9.7% |  17.6% | 0.5× | 44.4% |   0.2125 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   14.5 | 0.0% | 0.026 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   17 |   35.4 | 0.0% | 0.009 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
| DEGRADED |   42 |  103.3 | 0.0% | 0.004 | 0.0 |       40 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |   84 |   63.1 | 0.0% | 0.011 | 0.0 |       80 |    - |   0.0% |    - | 0.0% |   0.0750 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   25 |   14.5 | 0.0% | 0.595 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |   17 |   35.4 | 0.0% | 0.553 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   42 |  103.3 | 0.0% | 0.492 | 0.0 |       40 |    - |   0.0% |    - | 0.0% |   0.0250 |
|      ALL |   84 |   63.1 | 0.0% | 0.535 | 0.0 |       80 |    - |   0.0% |    - | 0.0% |   0.0375 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.9 | 33.3% | 0.671 | 0.7 |        5 | 0.0% |   0.0% |    - | 66.7% |   0.4000 |
|       OK |    6 |   37.2 | 33.3% | 0.637 | 0.5 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   19 |   69.1 | 36.8% | 0.726 | 0.4 |       17 | 0.0% |   0.0% |    - | 46.7% |   0.1176 |
|      ALL |   31 |   52.4 | 35.5% | 0.698 | 0.5 |       27 | 0.0% |   0.0% |    - | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.9 | 0.0% | 0.066 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.003 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   69.1 | 0.0% | 0.002 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   52.4 | 0.0% | 0.015 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   14.9 | 0.0% | 0.553 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.545 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   69.1 | 0.0% | 0.562 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.4 | 0.0% | 0.557 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available