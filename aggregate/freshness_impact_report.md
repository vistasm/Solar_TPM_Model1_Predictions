# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-02 UTC
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
🟡 **X+**: FRESH alert rate (2.1%) is 3.1× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       47 | 42.1% |  42.1% | 1.0× | 39.3% |   0.4043 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       28 | 18.2% |  40.0% | 1.0× | 39.1% |   0.1786 |
| DEGRADED |   69 |   92.7 | 34.8% | 0.678 | 0.4 |       67 | 0.0% |   0.0% |    - | 42.9% |   0.1642 |
|      ALL |  146 |   54.6 | 37.7% | 0.707 | 0.6 |      142 | 18.5% |  28.6% | 0.8× | 41.1% |   0.2465 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       47 | 50.0% |  12.5% | 2.9× | 2.6% |   0.1702 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0357 |
| DEGRADED |   69 |   92.7 | 0.0% | 0.013 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0597 |
|      ALL |  146 |   54.6 | 1.4% | 0.024 | 0.0 |      142 | 50.0% |   7.7% | 5.5× | 0.8% |   0.0915 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       47 | 0.0% |   0.0% |    - | 2.3% |   0.0851 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   69 |   92.7 | 0.0% | 0.495 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0149 |
|      ALL |  146 |   54.6 | 0.7% | 0.555 | 0.0 |      142 | 0.0% |   0.0% |    - | 0.7% |   0.0352 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.0 | 46.2% | 0.794 | 1.1 |       12 | 50.0% |  75.0% | 1.5× | 37.5% |   0.3333 |
|       OK |    8 |   24.7 | 50.0% | 0.800 | 0.6 |        7 | 33.3% |  50.0% | 1.2× | 40.0% |   0.2857 |
| DEGRADED |   10 |   68.1 | 10.0% | 0.532 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   31 |   33.8 | 35.5% | 0.711 | 0.7 |       27 | 40.0% |  57.1% | 1.5× | 30.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.0 | 15.4% | 0.116 | 0.1 |       12 | 50.0% |  50.0% | 3.0× | 10.0% |   0.1667 |
|       OK |    8 |   24.7 | 0.0% | 0.024 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   68.1 | 0.0% | 0.002 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.8 | 6.5% | 0.055 | 0.1 |       27 | 50.0% |  50.0% | 6.8× | 4.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   13.0 | 7.7% | 0.680 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
|       OK |    8 |   24.7 | 0.0% | 0.522 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   68.1 | 0.0% | 0.450 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.8 | 3.2% | 0.565 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available