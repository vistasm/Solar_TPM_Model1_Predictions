# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.4%) is 3.2× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.2× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 40.7% | 0.726 | 0.8 |       59 | 41.7% |  47.6% | 1.2× | 36.8% |   0.3559 |
|       OK |   35 |   32.9 | 40.0% | 0.722 | 0.6 |       35 | 14.3% |  40.0% | 1.0× | 40.0% |   0.1429 |
| DEGRADED |   96 |   93.9 | 31.2% | 0.657 | 0.3 |       92 | 6.7% |  11.8% | 0.4× | 37.3% |   0.1848 |
|      ALL |  190 |   57.8 | 35.8% | 0.691 | 0.5 |      186 | 20.6% |  32.6% | 0.9× | 37.8% |   0.2312 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 3.4% | 0.039 | 0.0 |       59 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1525 |
|       OK |   35 |   32.9 | 0.0% | 0.013 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
| DEGRADED |   96 |   93.9 | 0.0% | 0.011 | 0.0 |       92 |    - |   0.0% |    - | 0.0% |   0.0543 |
|      ALL |  190 |   57.8 | 1.1% | 0.020 | 0.0 |      186 | 50.0% |   6.7% | 6.2× | 0.6% |   0.0806 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 1.7% | 0.629 | 0.0 |       59 | 0.0% |   0.0% |    - | 1.8% |   0.0678 |
|       OK |   35 |   32.9 | 0.0% | 0.557 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   96 |   93.9 | 0.0% | 0.508 | 0.0 |       92 |    - |   0.0% |    - | 0.0% |   0.0109 |
|      ALL |  190 |   57.8 | 0.5% | 0.554 | 0.0 |      186 | 0.0% |   0.0% |    - | 0.5% |   0.0269 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.3 | 55.6% | 0.716 | 0.7 |        9 | 40.0% | 100.0% | 1.8× | 42.9% |   0.2222 |
|       OK |    3 |   40.0 | 33.3% | 0.594 | 0.3 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   18 |   70.7 | 27.8% | 0.600 | 0.4 |       14 | 40.0% |  40.0% | 1.1× | 33.3% |   0.3571 |
|      ALL |   30 |   50.7 | 36.7% | 0.634 | 0.5 |       26 | 36.4% |  57.1% | 1.4× | 36.8% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.3 | 0.0% | 0.002 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    3 |   40.0 | 0.0% | 0.002 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   70.7 | 0.0% | 0.011 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   30 |   50.7 | 0.0% | 0.007 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.3 | 0.0% | 0.591 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   40.0 | 0.0% | 0.566 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   70.7 | 0.0% | 0.545 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   50.7 | 0.0% | 0.561 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available