# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-03 UTC
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
|    FRESH |   36 |   13.5 | 38.9% | 0.718 | 0.7 |       32 | 20.0% |  16.7% | 0.5× | 40.0% |   0.3750 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  116 |   59.8 | 38.8% | 0.708 | 0.6 |      112 | 7.3% |  12.0% | 0.3× | 43.7% |   0.2232 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   36 |   13.5 | 0.0% | 0.031 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  116 |   59.8 | 0.0% | 0.019 | 0.0 |      112 |    - |   0.0% |    - | 0.0% |   0.0804 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   36 |   13.5 | 0.0% | 0.635 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0938 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  116 |   59.8 | 0.0% | 0.556 | 0.0 |      112 |    - |   0.0% |    - | 0.0% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.4 | 54.5% | 0.766 | 1.3 |        7 | 0.0% |   0.0% |    - | 40.0% |   0.2857 |
|       OK |    4 |   33.3 | 25.0% | 0.662 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 37.5% | 0.690 | 0.4 |       16 | 0.0% |   0.0% |    - | 46.2% |   0.1875 |
|      ALL |   31 |   49.7 | 41.9% | 0.714 | 0.7 |       27 | 0.0% |   0.0% |    - | 40.9% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.4 | 0.0% | 0.042 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   33.3 | 0.0% | 0.014 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.043 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   49.7 | 0.0% | 0.039 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   11.4 | 0.0% | 0.726 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    4 |   33.3 | 0.0% | 0.632 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.1 | 0.0% | 0.529 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.7 | 0.0% | 0.613 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available