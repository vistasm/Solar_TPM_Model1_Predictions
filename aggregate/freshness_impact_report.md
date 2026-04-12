# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-12 UTC
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
|    FRESH |   14 |   15.0 | 7.1% | 0.628 | 0.1 |       13 | 100.0% |  14.3% | 1.9× | 0.0% |   0.5385 |
|       OK |    9 |   36.9 | 44.4% | 0.741 | 0.7 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |   11 |   56.4 | 63.6% | 0.745 | 0.7 |        9 | 0.0% |   0.0% |    - | 75.0% |   0.1111 |
|      ALL |   34 |   34.2 | 35.3% | 0.696 | 0.4 |       30 | 9.1% |  10.0% | 0.3× | 50.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    9 |   36.9 | 0.0% | 0.009 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   56.4 | 0.0% | 0.004 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   34 |   34.2 | 0.0% | 0.007 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    9 |   36.9 | 0.0% | 0.527 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   56.4 | 0.0% | 0.462 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   34 |   34.2 | 0.0% | 0.510 | 0.0 |       30 |    - |   0.0% |    - | 0.0% |   0.0333 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.8 | 7.7% | 0.616 | 0.1 |       12 | 100.0% |  14.3% | 1.7× | 0.0% |   0.5833 |
|       OK |    7 |   36.7 | 28.6% | 0.681 | 0.3 |        6 | 0.0% |   0.0% |    - | 50.0% |   0.3333 |
| DEGRADED |   11 |   56.4 | 63.6% | 0.745 | 0.7 |        9 | 0.0% |   0.0% |    - | 75.0% |   0.1111 |
|      ALL |   31 |   34.5 | 32.3% | 0.676 | 0.3 |       27 | 11.1% |  10.0% | 0.3× | 47.1% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.8 | 0.0% | 0.008 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    7 |   36.7 | 0.0% | 0.011 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   56.4 | 0.0% | 0.004 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.5 | 0.0% | 0.007 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.8 | 0.0% | 0.548 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    7 |   36.7 | 0.0% | 0.539 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   56.4 | 0.0% | 0.462 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.5 | 0.0% | 0.515 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available