# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-07 UTC
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
|    FRESH |   13 |   14.6 | 7.7% | 0.641 | 0.1 |       13 | 100.0% |  14.3% | 1.9× | 0.0% |   0.5385 |
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |    8 |   55.3 | 62.5% | 0.738 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   29 |   31.7 | 34.5% | 0.702 | 0.5 |       25 | 14.3% |  10.0% | 0.4× | 40.0% |   0.4000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.008 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   55.3 | 0.0% | 0.004 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   31.7 | 0.0% | 0.008 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.542 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   55.3 | 0.0% | 0.464 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   31.7 | 0.0% | 0.523 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 7.7% | 0.641 | 0.1 |       13 | 100.0% |  14.3% | 1.9× | 0.0% |   0.5385 |
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |    8 |   55.3 | 62.5% | 0.738 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   29 |   31.7 | 34.5% | 0.702 | 0.5 |       25 | 14.3% |  10.0% | 0.4× | 40.0% |   0.4000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.008 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   55.3 | 0.0% | 0.004 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   31.7 | 0.0% | 0.008 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.542 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |   55.3 | 0.0% | 0.464 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   31.7 | 0.0% | 0.523 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available