# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (40.0%) is 40.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 31.6% | 0.706 | 0.4 |       18 | 40.0% |  25.0% | 0.9× | 30.0% |   0.4444 |
|       OK |   11 |   34.3 | 45.5% | 0.758 | 0.9 |       10 | 20.0% |  33.3% | 0.7× | 57.1% |   0.3000 |
| DEGRADED |   24 |  129.8 | 41.7% | 0.698 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   54 |   69.7 | 38.9% | 0.713 | 0.5 |       50 | 15.8% |  23.1% | 0.6× | 43.2% |   0.2600 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.013 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |   11 |   34.3 | 0.0% | 0.012 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
| DEGRADED |   24 |  129.8 | 0.0% | 0.005 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   54 |   69.7 | 0.0% | 0.009 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.1000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.609 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |   11 |   34.3 | 0.0% | 0.557 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  129.8 | 0.0% | 0.439 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   54 |   69.7 | 0.0% | 0.523 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   12.6 | 62.5% | 0.778 | 0.9 |        7 | 25.0% |  33.3% | 0.6× | 75.0% |   0.4286 |
|       OK |    3 |   30.1 | 33.3% | 0.742 | 1.3 |        2 | 100.0% | 100.0% | 2.0× | 0.0% |   0.5000 |
| DEGRADED |   20 |  138.5 | 40.0% | 0.702 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   95.5 | 45.2% | 0.725 | 0.6 |       27 | 16.7% |  40.0% | 0.9× | 45.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   12.6 | 0.0% | 0.020 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    3 |   30.1 | 0.0% | 0.018 | 0.0 |        2 |    - |   0.0% |    - | 0.0% |   0.5000 |
| DEGRADED |   20 |  138.5 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   95.5 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   12.6 | 0.0% | 0.713 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    3 |   30.1 | 0.0% | 0.573 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  138.5 | 0.0% | 0.436 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   95.5 | 0.0% | 0.521 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available