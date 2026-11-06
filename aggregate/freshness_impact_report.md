# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-06 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 31.7% HIGHER than DEGRADED (10.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 4.0× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.6%) is 4.0× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   13.6 | 41.0% | 0.722 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  145 |  102.3 | 28.3% | 0.631 | 0.3 |      142 | 10.0% |  18.2% | 0.7× | 30.0% |   0.1549 |
|      ALL |  242 |   69.6 | 33.5% | 0.668 | 0.5 |      238 | 20.2% |  33.3% | 1.0× | 33.2% |   0.2017 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   13.6 | 3.3% | 0.038 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  145 |  102.3 | 0.0% | 0.013 | 0.0 |      142 |    - |   0.0% |    - | 0.0% |   0.0493 |
|      ALL |  242 |   69.6 | 0.8% | 0.019 | 0.0 |      238 | 50.0% |   5.9% | 7.0× | 0.4% |   0.0714 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   13.6 | 1.6% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  145 |  102.3 | 0.0% | 0.520 | 0.0 |      142 |    - |   0.0% |    - | 0.0% |   0.0070 |
|      ALL |  242 |   69.6 | 0.4% | 0.552 | 0.0 |      238 | 0.0% |   0.0% |    - | 0.4% |   0.0210 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.3 | 100.0% | 0.885 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  110.3 | 33.3% | 0.643 | 0.4 |       27 | 22.2% |  66.7% | 2.0× | 29.2% |   0.1111 |
|      ALL |   31 |  107.1 | 35.5% | 0.651 | 0.5 |       27 | 22.2% |  66.7% | 2.0× | 29.2% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.3 | 0.0% | 0.002 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  110.3 | 0.0% | 0.028 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   31 |  107.1 | 0.0% | 0.027 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    1 |   11.3 | 0.0% | 0.630 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   30 |  110.3 | 0.0% | 0.564 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  107.1 | 0.0% | 0.566 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available