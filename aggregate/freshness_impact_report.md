# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-10 UTC
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
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |   10 |   55.1 | 70.0% | 0.771 | 0.8 |        7 | 0.0% |   0.0% |    - | 83.3% |   0.1429 |
|      ALL |   32 |   32.8 | 37.5% | 0.707 | 0.5 |       28 | 10.0% |  10.0% | 0.3× | 50.0% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   55.1 | 0.0% | 0.004 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   32 |   32.8 | 0.0% | 0.007 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   55.1 | 0.0% | 0.479 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   32 |   32.8 | 0.0% | 0.523 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 7.1% | 0.628 | 0.1 |       13 | 100.0% |  14.3% | 1.9× | 0.0% |   0.5385 |
|       OK |    7 |   36.2 | 42.9% | 0.735 | 0.4 |        7 | 0.0% |   0.0% |    - | 60.0% |   0.2857 |
| DEGRADED |   10 |   55.1 | 70.0% | 0.771 | 0.8 |        7 | 0.0% |   0.0% |    - | 83.3% |   0.1429 |
|      ALL |   31 |   32.8 | 35.5% | 0.698 | 0.4 |       27 | 11.1% |  10.0% | 0.3× | 47.1% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.008 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    7 |   36.2 | 0.0% | 0.011 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   55.1 | 0.0% | 0.004 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.8 | 0.0% | 0.007 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   15.0 | 0.0% | 0.538 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|       OK |    7 |   36.2 | 0.0% | 0.567 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   55.1 | 0.0% | 0.479 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   32.8 | 0.0% | 0.525 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available