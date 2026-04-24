# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-24 UTC
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
|    FRESH |   15 |   14.3 | 13.3% | 0.645 | 0.1 |       14 | 100.0% |  14.3% | 2.0× | 0.0% |   0.5000 |
|       OK |    9 |   36.9 | 44.4% | 0.741 | 0.7 |        9 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |
| DEGRADED |   22 |  134.7 | 40.9% | 0.689 | 0.5 |       19 | 0.0% |   0.0% |    - | 44.4% |   0.0526 |
|      ALL |   46 |   76.3 | 32.6% | 0.685 | 0.4 |       42 | 7.7% |  10.0% | 0.3× | 37.5% |   0.2381 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   14.3 | 0.0% | 0.009 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   36.9 | 0.0% | 0.009 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.006 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   46 |   76.3 | 0.0% | 0.007 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0476 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   14.3 | 0.0% | 0.550 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   36.9 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   22 |  134.7 | 0.0% | 0.429 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   46 |   76.3 | 0.0% | 0.488 | 0.0 |       42 |    - |   0.0% |    - | 0.0% |   0.0238 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.5 | 22.2% | 0.644 | 0.2 |        8 | 100.0% |  25.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    4 |   37.2 | 50.0% | 0.748 | 0.5 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |   18 |  145.5 | 38.9% | 0.691 | 0.4 |       15 | 0.0% |      - |    - | 40.0% |   0.0000 |
|      ALL |   31 |   92.9 | 35.5% | 0.685 | 0.3 |       27 | 11.1% |  20.0% | 0.6× | 36.4% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.5 | 0.0% | 0.012 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    4 |   37.2 | 0.0% | 0.017 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.006 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.9 | 0.0% | 0.009 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   12.5 | 0.0% | 0.649 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    4 |   37.2 | 0.0% | 0.664 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  145.5 | 0.0% | 0.423 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   92.9 | 0.0% | 0.520 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available