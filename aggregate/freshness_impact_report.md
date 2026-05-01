# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-01 UTC
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
|    FRESH |   19 |   14.3 | 31.6% | 0.706 | 0.4 |       17 | 25.0% |  14.3% | 0.6× | 30.0% |   0.4118 |
|       OK |   11 |   34.3 | 45.5% | 0.758 | 0.9 |       10 | 20.0% |  33.3% | 0.7× | 57.1% |   0.3000 |
| DEGRADED |   23 |  131.7 | 43.5% | 0.696 | 0.5 |       22 | 0.0% |   0.0% |    - | 45.0% |   0.0909 |
|      ALL |   53 |   69.4 | 39.6% | 0.712 | 0.6 |       49 | 11.1% |  16.7% | 0.5× | 43.2% |   0.2449 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.013 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1765 |
|       OK |   11 |   34.3 | 0.0% | 0.012 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
| DEGRADED |   23 |  131.7 | 0.0% | 0.005 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   53 |   69.4 | 0.0% | 0.010 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.1020 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   14.3 | 0.0% | 0.609 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |
|       OK |   11 |   34.3 | 0.0% | 0.557 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |  131.7 | 0.0% | 0.435 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
|      ALL |   53 |   69.4 | 0.0% | 0.522 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 55.6% | 0.761 | 0.8 |        7 | 0.0% |   0.0% |    - | 60.0% |   0.2857 |
|       OK |    3 |   30.1 | 33.3% | 0.742 | 1.3 |        2 | 100.0% | 100.0% | 2.0× | 0.0% |   0.5000 |
| DEGRADED |   19 |  141.2 | 42.1% | 0.699 | 0.4 |       18 | 0.0% |   0.0% |    - | 41.2% |   0.0556 |
|      ALL |   31 |   93.3 | 45.2% | 0.721 | 0.6 |       27 | 9.1% |  25.0% | 0.6× | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 0.0% | 0.018 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.2857 |
|       OK |    3 |   30.1 | 0.0% | 0.018 | 0.0 |        2 |    - |   0.0% |    - | 0.0% |   0.5000 |
| DEGRADED |   19 |  141.2 | 0.0% | 0.006 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   93.3 | 0.0% | 0.011 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   13.4 | 0.0% | 0.716 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    3 |   30.1 | 0.0% | 0.573 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  141.2 | 0.0% | 0.430 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   31 |   93.3 | 0.0% | 0.527 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available