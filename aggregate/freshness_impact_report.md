# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-23 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (20.0%) is 20.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 31.2% | 0.690 | 0.5 |       32 | 20.0% |  16.7% | 0.5× | 40.0% |   0.3750 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   53 |   94.4 | 37.7% | 0.691 | 0.4 |       49 | 0.0% |   0.0% |    - | 43.9% |   0.1633 |
|      ALL |  106 |   58.5 | 35.9% | 0.694 | 0.5 |      102 | 8.3% |  13.0% | 0.4× | 41.8% |   0.2255 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.022 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   53 |   94.4 | 0.0% | 0.004 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  106 |   58.5 | 0.0% | 0.010 | 0.0 |      102 |    - |   0.0% |    - | 0.0% |   0.0784 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.600 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0938 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   53 |   94.4 | 0.0% | 0.483 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  106 |   58.5 | 0.0% | 0.535 | 0.0 |      102 |    - |   0.0% |    - | 0.0% |   0.0392 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 25.0% | 0.646 | 0.4 |        8 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
|       OK |    5 |   36.0 | 40.0% | 0.720 | 0.4 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   18 |   75.4 | 38.9% | 0.683 | 0.4 |       14 | 0.0% |   0.0% |    - | 50.0% |   0.2857 |
|      ALL |   31 |   53.6 | 35.5% | 0.680 | 0.4 |       27 | 0.0% |   0.0% |    - | 42.9% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 0.0% | 0.006 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   36.0 | 0.0% | 0.012 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   75.4 | 0.0% | 0.002 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   53.6 | 0.0% | 0.004 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 0.0% | 0.610 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   36.0 | 0.0% | 0.620 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   75.4 | 0.0% | 0.503 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.6 | 0.0% | 0.549 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available