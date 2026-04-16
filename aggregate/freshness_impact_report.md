# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-16 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 7.1% | 0.628 | 0.1 |       14 | 100.0% |  14.3% | 2.0× | 0.0% |   0.5000 |
|       OK |    9 |   36.9 | 44.4% | 0.741 | 0.7 |        9 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |
| DEGRADED |   15 |   75.8 | 53.3% | 0.714 | 0.6 |       11 | 0.0% |   0.0% |    - | 70.0% |   0.0909 |
|      ALL |   38 |   44.2 | 34.2% | 0.689 | 0.4 |       34 | 8.3% |  10.0% | 0.3× | 45.8% |   0.2941 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   36.9 | 0.0% | 0.009 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   75.8 | 0.0% | 0.003 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   38 |   44.2 | 0.0% | 0.006 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0588 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   36.9 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   75.8 | 0.0% | 0.436 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   38 |   44.2 | 0.0% | 0.495 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.8 | 9.1% | 0.636 | 0.1 |       11 | 100.0% |  16.7% | 1.8× | 0.0% |   0.5455 |
|       OK |    6 |   37.2 | 33.3% | 0.687 | 0.3 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
| DEGRADED |   14 |   76.5 | 57.1% | 0.724 | 0.6 |       10 | 0.0% |      - |    - | 70.0% |   0.0000 |
|      ALL |   31 |   47.0 | 35.5% | 0.685 | 0.4 |       27 | 10.0% |  14.3% | 0.4× | 45.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.8 | 0.0% | 0.009 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |    6 |   37.2 | 0.0% | 0.012 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   76.5 | 0.0% | 0.003 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.0 | 0.0% | 0.007 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.8 | 0.0% | 0.575 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    6 |   37.2 | 0.0% | 0.558 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   76.5 | 0.0% | 0.432 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.0 | 0.0% | 0.507 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available