# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.4%) is 3.1× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.1× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 40.7% | 0.726 | 0.8 |       56 | 41.7% |  47.6% | 1.1× | 40.0% |   0.3750 |
|       OK |   34 |   32.6 | 41.2% | 0.728 | 0.6 |       33 | 14.3% |  40.0% | 0.9× | 42.9% |   0.1515 |
| DEGRADED |   90 |   90.5 | 33.3% | 0.676 | 0.4 |       90 | 6.7% |  11.8% | 0.3× | 38.4% |   0.1889 |
|      ALL |  183 |   55.0 | 37.2% | 0.702 | 0.5 |      179 | 20.6% |  32.6% | 0.9× | 39.7% |   0.2402 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 3.4% | 0.039 | 0.0 |       56 | 50.0% |  11.1% | 3.1× | 2.1% |   0.1607 |
|       OK |   34 |   32.6 | 0.0% | 0.013 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0303 |
| DEGRADED |   90 |   90.5 | 0.0% | 0.012 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |  183 |   55.0 | 1.1% | 0.021 | 0.0 |      179 | 50.0% |   6.7% | 6.0× | 0.6% |   0.0838 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 1.7% | 0.629 | 0.0 |       56 | 0.0% |   0.0% |    - | 1.9% |   0.0714 |
|       OK |   34 |   32.6 | 0.0% | 0.558 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   90 |   90.5 | 0.0% | 0.507 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0111 |
|      ALL |  183 |   55.0 | 0.5% | 0.556 | 0.0 |      179 | 0.0% |   0.0% |    - | 0.6% |   0.0279 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.2 | 45.5% | 0.694 | 0.6 |        8 | 40.0% | 100.0% | 1.6× | 50.0% |   0.2500 |
|       OK |    5 |   35.1 | 40.0% | 0.706 | 0.4 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   14 |   39.8 | 35.7% | 0.709 | 0.5 |       14 | 40.0% |  40.0% | 1.1× | 33.3% |   0.3571 |
|      ALL |   30 |   29.6 | 40.0% | 0.703 | 0.5 |       26 | 33.3% |  57.1% | 1.2× | 42.1% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.2 | 0.0% | 0.002 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   35.1 | 0.0% | 0.012 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   39.8 | 0.0% | 0.014 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   30 |   29.6 | 0.0% | 0.009 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   14.2 | 0.0% | 0.579 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.1 | 0.0% | 0.575 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   39.8 | 0.0% | 0.555 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   29.6 | 0.0% | 0.567 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available