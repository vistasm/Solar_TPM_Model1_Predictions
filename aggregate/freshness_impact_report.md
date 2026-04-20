# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-20 UTC
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
| DEGRADED |   19 |  107.2 | 42.1% | 0.684 | 0.5 |       15 | 0.0% |   0.0% |    - | 57.1% |   0.0667 |
|      ALL |   42 |   61.4 | 30.9% | 0.677 | 0.4 |       38 | 7.7% |  10.0% | 0.3× | 42.9% |   0.2632 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    9 |   36.9 | 0.0% | 0.009 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  107.2 | 0.0% | 0.006 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   42 |   61.4 | 0.0% | 0.007 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.0526 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|       OK |    9 |   36.9 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  107.2 | 0.0% | 0.433 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   42 |   61.4 | 0.0% | 0.488 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.0263 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 12.5% | 0.615 | 0.1 |        8 | 100.0% |  25.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    5 |   35.7 | 40.0% | 0.730 | 0.4 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
| DEGRADED |   18 |  109.5 | 44.4% | 0.690 | 0.5 |       14 | 0.0% |      - |    - | 57.1% |   0.0000 |
|      ALL |   31 |   72.8 | 35.5% | 0.677 | 0.4 |       27 | 9.1% |  20.0% | 0.5× | 45.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 0.0% | 0.012 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    5 |   35.7 | 0.0% | 0.014 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  109.5 | 0.0% | 0.006 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.8 | 0.0% | 0.009 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   13.5 | 0.0% | 0.640 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   35.7 | 0.0% | 0.622 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |  109.5 | 0.0% | 0.430 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.8 | 0.0% | 0.515 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available