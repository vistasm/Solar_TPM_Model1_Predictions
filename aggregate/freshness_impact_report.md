# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-19 UTC
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
| DEGRADED |   18 |   98.7 | 44.4% | 0.698 | 0.5 |       14 | 0.0% |   0.0% |    - | 61.5% |   0.0714 |
|      ALL |   41 |   56.6 | 31.7% | 0.683 | 0.4 |       37 | 7.7% |  10.0% | 0.3× | 44.4% |   0.2703 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   36.9 | 0.0% | 0.009 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   98.7 | 0.0% | 0.007 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   41 |   56.6 | 0.0% | 0.007 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0541 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   36.9 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   98.7 | 0.0% | 0.440 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   41 |   56.6 | 0.0% | 0.493 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0270 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 12.5% | 0.615 | 0.1 |        8 | 100.0% |  25.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    6 |   37.2 | 33.3% | 0.687 | 0.3 |        6 | 0.0% |   0.0% |    - | 40.0% |   0.1667 |
| DEGRADED |   17 |  100.6 | 47.1% | 0.705 | 0.5 |       13 | 0.0% |      - |    - | 61.5% |   0.0000 |
|      ALL |   31 |   65.9 | 35.5% | 0.678 | 0.4 |       27 | 9.1% |  20.0% | 0.5× | 45.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 0.0% | 0.012 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    6 |   37.2 | 0.0% | 0.012 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  100.6 | 0.0% | 0.007 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.9 | 0.0% | 0.009 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 0.0% | 0.640 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   37.2 | 0.0% | 0.558 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  100.6 | 0.0% | 0.437 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   65.9 | 0.0% | 0.513 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available