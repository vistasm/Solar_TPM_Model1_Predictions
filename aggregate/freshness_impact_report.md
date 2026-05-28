# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-28 UTC
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
| DEGRADED |   40 |  102.7 | 42.5% | 0.716 | 0.5 |       36 | 0.0% |   0.0% |    - | 43.8% |   0.1111 |
|      ALL |   80 |   62.5 | 38.8% | 0.710 | 0.5 |       76 | 10.7% |  17.6% | 0.5× | 42.4% |   0.2237 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
| DEGRADED |   40 |  102.7 | 0.0% | 0.004 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   80 |   62.5 | 0.0% | 0.012 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0789 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   40 |  102.7 | 0.0% | 0.488 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
|      ALL |   80 |   62.5 | 0.0% | 0.533 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0395 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 57.1% | 0.757 | 1.0 |        7 | 25.0% |  33.3% | 0.6× | 75.0% |   0.4286 |
|       OK |    6 |   36.1 | 16.7% | 0.603 | 0.3 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   18 |   63.4 | 44.4% | 0.748 | 0.4 |       14 | 0.0% |   0.0% |    - | 41.7% |   0.1429 |
|      ALL |   31 |   47.2 | 41.9% | 0.722 | 0.6 |       27 | 10.0% |  20.0% | 0.5× | 40.9% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.064 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.005 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   63.4 | 0.0% | 0.002 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   47.2 | 0.0% | 0.017 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   15.1 | 0.0% | 0.615 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.536 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   63.4 | 0.0% | 0.559 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.2 | 0.0% | 0.567 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available