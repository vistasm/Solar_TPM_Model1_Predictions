# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-03 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 3.1× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.1× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       47 | 42.1% |  42.1% | 1.0× | 39.3% |   0.4043 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       28 | 18.2% |  40.0% | 1.0× | 39.1% |   0.1786 |
| DEGRADED |   70 |   92.6 | 35.7% | 0.681 | 0.4 |       68 | 0.0% |   0.0% |    - | 42.9% |   0.1765 |
|      ALL |  147 |   54.9 | 38.1% | 0.708 | 0.6 |      143 | 18.5% |  27.8% | 0.7× | 41.1% |   0.2517 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       47 | 50.0% |  12.5% | 2.9× | 2.6% |   0.1702 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |
| DEGRADED |   70 |   92.6 | 0.0% | 0.013 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  147 |   54.9 | 1.4% | 0.024 | 0.0 |      143 | 50.0% |   7.7% | 5.5× | 0.8% |   0.0909 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       47 | 0.0% |   0.0% |    - | 2.3% |   0.0851 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   70 |   92.6 | 0.0% | 0.496 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0147 |
|      ALL |  147 |   54.9 | 0.7% | 0.555 | 0.0 |      143 | 0.0% |   0.0% |    - | 0.7% |   0.0350 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.5 | 41.7% | 0.778 | 1.0 |       11 | 40.0% |  66.7% | 1.5× | 37.5% |   0.2727 |
|       OK |    8 |   24.7 | 50.0% | 0.800 | 0.6 |        7 | 33.3% |  50.0% | 1.2× | 40.0% |   0.2857 |
| DEGRADED |   11 |   69.6 | 18.2% | 0.568 | 0.2 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|      ALL |   31 |   36.3 | 35.5% | 0.709 | 0.6 |       27 | 33.3% |  42.9% | 1.3× | 30.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.5 | 16.7% | 0.099 | 0.2 |       11 | 50.0% | 100.0% | 5.5× | 10.0% |   0.0909 |
|       OK |    8 |   24.7 | 0.0% | 0.024 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   69.6 | 0.0% | 0.003 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.3 | 6.5% | 0.046 | 0.1 |       27 | 50.0% | 100.0% | 13.5× | 3.9% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   13.5 | 8.3% | 0.654 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|       OK |    8 |   24.7 | 0.0% | 0.522 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   69.6 | 0.0% | 0.460 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.3 | 3.2% | 0.551 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available