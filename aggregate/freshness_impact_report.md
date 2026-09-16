# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-16 UTC
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
| DEGRADED |   94 |   91.6 | 31.9% | 0.664 | 0.4 |       91 | 6.7% |  11.8% | 0.4× | 37.8% |   0.1868 |
|      ALL |  188 |   56.2 | 36.2% | 0.694 | 0.5 |      185 | 20.6% |  32.6% | 0.9× | 38.0% |   0.2324 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 3.4% | 0.039 | 0.0 |       59 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1525 |
|       OK |   35 |   32.9 | 0.0% | 0.013 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
| DEGRADED |   94 |   91.6 | 0.0% | 0.011 | 0.0 |       91 |    - |   0.0% |    - | 0.0% |   0.0549 |
|      ALL |  188 |   56.2 | 1.1% | 0.021 | 0.0 |      185 | 50.0% |   6.7% | 6.2× | 0.6% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 1.7% | 0.629 | 0.0 |       59 | 0.0% |   0.0% |    - | 1.8% |   0.0678 |
|       OK |   35 |   32.9 | 0.0% | 0.557 | 0.0 |       35 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   94 |   91.6 | 0.0% | 0.508 | 0.0 |       91 |    - |   0.0% |    - | 0.0% |   0.0110 |
|      ALL |  188 |   56.2 | 0.5% | 0.555 | 0.0 |      185 | 0.0% |   0.0% |    - | 0.6% |   0.0270 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 50.0% | 0.721 | 0.6 |       10 | 40.0% | 100.0% | 2.0× | 37.5% |   0.2000 |
|       OK |    4 |   33.2 | 25.0% | 0.628 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   16 |   54.4 | 31.2% | 0.630 | 0.4 |       13 | 40.0% |  40.0% | 1.0× | 37.5% |   0.3846 |
|      ALL |   30 |   38.1 | 36.7% | 0.660 | 0.5 |       27 | 36.4% |  57.1% | 1.4× | 35.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 0.0% | 0.002 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    4 |   33.2 | 0.0% | 0.014 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   54.4 | 0.0% | 0.012 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   30 |   38.1 | 0.0% | 0.009 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 0.0% | 0.587 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.2 | 0.0% | 0.568 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   54.4 | 0.0% | 0.549 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   38.1 | 0.0% | 0.565 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available