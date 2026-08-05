# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-05 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 3.1× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.1× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   29 |   32.1 | 41.4% | 0.731 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   72 |   93.4 | 34.7% | 0.683 | 0.4 |       68 | 0.0% |   0.0% |    - | 42.9% |   0.1765 |
|      ALL |  149 |   55.7 | 37.6% | 0.709 | 0.6 |      145 | 18.2% |  27.8% | 0.7× | 41.3% |   0.2483 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   29 |   32.1 | 0.0% | 0.014 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   72 |   93.4 | 0.0% | 0.012 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0588 |
|      ALL |  149 |   55.7 | 1.3% | 0.024 | 0.0 |      145 | 50.0% |   7.7% | 5.6× | 0.8% |   0.0897 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   29 |   32.1 | 0.0% | 0.555 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   72 |   93.4 | 0.0% | 0.499 | 0.0 |       68 |    - |   0.0% |    - | 0.0% |   0.0147 |
|      ALL |  149 |   55.7 | 0.7% | 0.555 | 0.0 |      145 | 0.0% |   0.0% |    - | 0.7% |   0.0345 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   15.3 | 30.0% | 0.738 | 0.5 |       10 | 0.0% |   0.0% |    - | 33.3% |   0.1000 |
|       OK |    8 |   24.7 | 50.0% | 0.800 | 0.6 |        8 | 25.0% |  50.0% | 1.0× | 50.0% |   0.2500 |
| DEGRADED |   13 |   77.5 | 15.4% | 0.597 | 0.1 |        9 | 0.0% |   0.0% |    - | 14.3% |   0.2222 |
|      ALL |   31 |   43.8 | 29.0% | 0.695 | 0.4 |       27 | 12.5% |  20.0% | 0.7× | 31.8% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   15.3 | 0.0% | 0.006 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   24.7 | 0.0% | 0.024 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   77.5 | 0.0% | 0.003 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.8 | 0.0% | 0.009 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   15.3 | 0.0% | 0.587 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   24.7 | 0.0% | 0.522 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   13 |   77.5 | 0.0% | 0.478 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.8 | 0.0% | 0.524 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available