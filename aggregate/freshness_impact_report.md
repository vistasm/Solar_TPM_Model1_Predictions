# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 3.0× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.0× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       47 | 42.1% |  42.1% | 1.0× | 39.3% |   0.4043 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       27 | 18.2% |  40.0% | 1.0× | 40.9% |   0.1852 |
| DEGRADED |   68 |   93.2 | 35.3% | 0.677 | 0.4 |       67 | 0.0% |   0.0% |    - | 42.9% |   0.1642 |
|      ALL |  145 |   54.6 | 37.9% | 0.707 | 0.6 |      141 | 18.5% |  28.6% | 0.8× | 41.5% |   0.2482 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       47 | 50.0% |  12.5% | 2.9× | 2.6% |   0.1702 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
| DEGRADED |   68 |   93.2 | 0.0% | 0.013 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0597 |
|      ALL |  145 |   54.6 | 1.4% | 0.025 | 0.0 |      141 | 50.0% |   7.7% | 5.4× | 0.8% |   0.0922 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       47 | 0.0% |   0.0% |    - | 2.3% |   0.0851 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   68 |   93.2 | 0.0% | 0.494 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0149 |
|      ALL |  145 |   54.6 | 0.7% | 0.555 | 0.0 |      141 | 0.0% |   0.0% |    - | 0.7% |   0.0355 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.3 | 50.0% | 0.808 | 1.4 |       13 | 57.1% |  80.0% | 1.5× | 37.5% |   0.3846 |
|       OK |    8 |   24.7 | 50.0% | 0.800 | 0.6 |        6 | 33.3% |  50.0% | 1.0× | 50.0% |   0.3333 |
| DEGRADED |    9 |   68.9 | 11.1% | 0.512 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   31 |   31.9 | 38.7% | 0.720 | 0.8 |       27 | 45.5% |  62.5% | 1.5× | 31.6% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.3 | 14.3% | 0.109 | 0.1 |       13 | 50.0% |  50.0% | 3.2× | 9.1% |   0.1538 |
|       OK |    8 |   24.7 | 0.0% | 0.024 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   68.9 | 0.0% | 0.001 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.9 | 6.5% | 0.056 | 0.1 |       27 | 50.0% |  50.0% | 6.8× | 4.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.3 | 7.1% | 0.702 | 0.1 |       13 | 0.0% |      - |    - | 7.7% |   0.0000 |
|       OK |    8 |   24.7 | 0.0% | 0.522 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   68.9 | 0.0% | 0.437 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.9 | 3.2% | 0.579 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available