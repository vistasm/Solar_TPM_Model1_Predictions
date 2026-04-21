# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-21 UTC
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
| DEGRADED |   20 |  116.1 | 40.0% | 0.675 | 0.5 |       16 | 0.0% |   0.0% |    - | 53.3% |   0.0625 |
|      ALL |   43 |   66.6 | 30.2% | 0.673 | 0.4 |       39 | 7.7% |  10.0% | 0.3× | 41.4% |   0.2564 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   36.9 | 0.0% | 0.009 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  116.1 | 0.0% | 0.006 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   43 |   66.6 | 0.0% | 0.007 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0513 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   36.9 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  116.1 | 0.0% | 0.427 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   43 |   66.6 | 0.0% | 0.484 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 12.5% | 0.615 | 0.1 |        8 | 100.0% |  25.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    5 |   35.7 | 40.0% | 0.730 | 0.4 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
| DEGRADED |   18 |  121.5 | 44.4% | 0.705 | 0.5 |       14 | 0.0% |      - |    - | 57.1% |   0.0000 |
|      ALL |   31 |   79.8 | 35.5% | 0.686 | 0.4 |       27 | 9.1% |  20.0% | 0.5× | 45.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 0.0% | 0.012 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    5 |   35.7 | 0.0% | 0.014 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  121.5 | 0.0% | 0.007 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   79.8 | 0.0% | 0.009 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 0.0% | 0.640 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   35.7 | 0.0% | 0.622 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  121.5 | 0.0% | 0.433 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   79.8 | 0.0% | 0.517 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available