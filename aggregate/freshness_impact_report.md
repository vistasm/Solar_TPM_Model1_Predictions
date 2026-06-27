# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (20.0%) is 20.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 31.2% | 0.690 | 0.5 |       32 | 20.0% |  16.7% | 0.5× | 40.0% |   0.3750 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   57 |   94.4 | 40.4% | 0.702 | 0.4 |       53 | 0.0% |   0.0% |    - | 45.5% |   0.1698 |
|      ALL |  110 |   59.8 | 37.3% | 0.699 | 0.5 |      106 | 7.9% |  12.5% | 0.3× | 42.7% |   0.2264 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.022 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   57 |   94.4 | 0.0% | 0.009 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0755 |
|      ALL |  110 |   59.8 | 0.0% | 0.013 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0849 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.600 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0938 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   57 |   94.4 | 0.0% | 0.496 | 0.0 |       53 |    - |   0.0% |    - | 0.0% |   0.0189 |
|      ALL |  110 |   59.8 | 0.0% | 0.540 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0377 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 25.0% | 0.646 | 0.4 |        8 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
|       OK |    5 |   36.0 | 40.0% | 0.720 | 0.4 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   18 |   78.7 | 38.9% | 0.685 | 0.4 |       14 | 0.0% |   0.0% |    - | 44.4% |   0.3571 |
|      ALL |   31 |   55.5 | 35.5% | 0.681 | 0.4 |       27 | 0.0% |   0.0% |    - | 40.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 0.0% | 0.006 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   36.0 | 0.0% | 0.012 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   78.7 | 0.0% | 0.020 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   55.5 | 0.0% | 0.015 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 0.0% | 0.610 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   36.0 | 0.0% | 0.620 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   78.7 | 0.0% | 0.521 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   55.5 | 0.0% | 0.560 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available