# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-05 UTC
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
|    FRESH |   13 |   14.6 | 7.7% | 0.641 | 0.1 |       11 | 100.0% |  20.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |    6 |   59.4 | 66.7% | 0.734 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   27 |   30.9 | 33.3% | 0.698 | 0.4 |       23 | 14.3% |  12.5% | 0.4× | 40.0% |   0.3478 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.008 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   59.4 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.9 | 0.0% | 0.007 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.542 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   59.4 | 0.0% | 0.466 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.9 | 0.0% | 0.528 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 7.7% | 0.641 | 0.1 |       11 | 100.0% |  20.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |    6 |   59.4 | 66.7% | 0.734 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   27 |   30.9 | 33.3% | 0.698 | 0.4 |       23 | 14.3% |  12.5% | 0.4× | 40.0% |   0.3478 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.008 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   59.4 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.9 | 0.0% | 0.007 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.542 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    6 |   59.4 | 0.0% | 0.466 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |   30.9 | 0.0% | 0.528 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available