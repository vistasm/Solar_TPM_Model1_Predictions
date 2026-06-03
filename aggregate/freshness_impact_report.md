# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-03 UTC
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
|    FRESH |   26 |   14.1 | 30.8% | 0.698 | 0.5 |       25 | 25.0% |  20.0% | 0.6× | 40.0% |   0.4000 |
|       OK |   17 |   35.4 | 41.2% | 0.715 | 0.8 |       16 | 16.7% |  33.3% | 0.9× | 38.5% |   0.1875 |
| DEGRADED |   43 |  103.1 | 39.5% | 0.707 | 0.4 |       41 | 0.0% |   0.0% |    - | 47.2% |   0.1220 |
|      ALL |   86 |   62.8 | 37.2% | 0.706 | 0.5 |       82 | 9.7% |  16.7% | 0.4× | 43.8% |   0.2195 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   14.1 | 0.0% | 0.025 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1200 |
|       OK |   17 |   35.4 | 0.0% | 0.009 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.004 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.0488 |
|      ALL |   86 |   62.8 | 0.0% | 0.011 | 0.0 |       82 |    - |   0.0% |    - | 0.0% |   0.0732 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   14.1 | 0.0% | 0.591 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|       OK |   17 |   35.4 | 0.0% | 0.553 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.493 | 0.0 |       41 |    - |   0.0% |    - | 0.0% |   0.0244 |
|      ALL |   86 |   62.8 | 0.0% | 0.534 | 0.0 |       82 |    - |   0.0% |    - | 0.0% |   0.0366 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.8 | 33.3% | 0.660 | 0.7 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
|       OK |    6 |   37.2 | 33.3% | 0.637 | 0.5 |        5 | 0.0% |      - |    - | 20.0% |   0.0000 |
| DEGRADED |   19 |   69.4 | 36.8% | 0.718 | 0.4 |       17 | 0.0% |   0.0% |    - | 50.0% |   0.1765 |
|      ALL |   31 |   52.4 | 35.5% | 0.691 | 0.5 |       27 | 0.0% |   0.0% |    - | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.8 | 0.0% | 0.065 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.003 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   69.4 | 0.0% | 0.002 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |   31 |   52.4 | 0.0% | 0.014 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.8 | 0.0% | 0.540 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   37.2 | 0.0% | 0.545 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   69.4 | 0.0% | 0.561 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.4 | 0.0% | 0.554 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available