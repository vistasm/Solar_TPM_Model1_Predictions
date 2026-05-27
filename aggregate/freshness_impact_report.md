# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-27 UTC
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
|    FRESH |   24 |   14.1 | 33.3% | 0.705 | 0.5 |       24 | 25.0% |  20.0% | 0.6× | 42.9% |   0.4167 |
|       OK |   16 |   34.6 | 37.5% | 0.700 | 0.8 |       16 | 16.7% |  33.3% | 0.9× | 38.5% |   0.1875 |
| DEGRADED |   39 |  101.7 | 41.0% | 0.709 | 0.4 |       35 | 0.0% |   0.0% |    - | 41.9% |   0.1143 |
|      ALL |   79 |   61.5 | 38.0% | 0.706 | 0.5 |       75 | 11.1% |  17.6% | 0.5× | 41.4% |   0.2267 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
| DEGRADED |   39 |  101.7 | 0.0% | 0.004 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0571 |
|      ALL |   79 |   61.5 | 0.0% | 0.012 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   39 |  101.7 | 0.0% | 0.485 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |   79 |   61.5 | 0.0% | 0.532 | 0.0 |       75 |    - |   0.0% |    - | 0.0% |   0.0400 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.1 | 62.5% | 0.782 | 1.0 |        8 | 20.0% |  33.3% | 0.5× | 80.0% |   0.3750 |
|       OK |    6 |   36.1 | 16.7% | 0.603 | 0.3 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   17 |   59.0 | 41.2% | 0.735 | 0.4 |       13 | 0.0% |   0.0% |    - | 36.4% |   0.1538 |
|      ALL |   31 |   42.9 | 41.9% | 0.722 | 0.6 |       27 | 10.0% |  20.0% | 0.5× | 40.9% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.1 | 0.0% | 0.066 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.005 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   59.0 | 0.0% | 0.002 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   42.9 | 0.0% | 0.019 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.1 | 0.0% | 0.643 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.536 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   59.0 | 0.0% | 0.557 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   42.9 | 0.0% | 0.575 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available