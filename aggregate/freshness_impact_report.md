# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (38.5%) is 26.6% HIGHER than DEGRADED (11.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.1%) is 3.9× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.6%) is 4.0× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 40.6% | 0.725 | 0.7 |       64 | 38.5% |  45.5% | 1.1× | 38.1% |   0.3438 |
|       OK |   39 |   33.1 | 43.6% | 0.736 | 0.6 |       39 | 17.6% |  50.0% | 1.1× | 42.4% |   0.1538 |
| DEGRADED |  151 |   99.4 | 28.5% | 0.632 | 0.3 |      147 | 11.9% |  20.8% | 0.7× | 30.1% |   0.1633 |
|      ALL |  254 |   67.5 | 33.9% | 0.671 | 0.5 |      250 | 21.2% |  34.6% | 1.0× | 33.8% |   0.2080 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 3.1% | 0.037 | 0.0 |       64 | 50.0% |  11.1% | 3.6× | 1.8% |   0.1406 |
|       OK |   39 |   33.1 | 0.0% | 0.015 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
| DEGRADED |  151 |   99.4 | 0.0% | 0.013 | 0.0 |      147 |    - |   0.0% |    - | 0.0% |   0.0476 |
|      ALL |  254 |   67.5 | 0.8% | 0.019 | 0.0 |      250 | 50.0% |   5.9% | 7.3× | 0.4% |   0.0680 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 1.6% | 0.624 | 0.0 |       64 | 0.0% |   0.0% |    - | 1.7% |   0.0625 |
|       OK |   39 |   33.1 | 0.0% | 0.560 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  151 |   99.4 | 0.0% | 0.521 | 0.0 |      147 |    - |   0.0% |    - | 0.0% |   0.0068 |
|      ALL |  254 |   67.5 | 0.4% | 0.553 | 0.0 |      250 | 0.0% |   0.0% |    - | 0.4% |   0.0200 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 50.0% | 0.818 | 0.5 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|       OK |    3 |   34.4 | 66.7% | 0.819 | 1.0 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   24 |   97.3 | 16.7% | 0.536 | 0.2 |       20 | 66.7% |  66.7% | 4.4× | 5.9% |   0.1500 |
|      ALL |   31 |   80.0 | 25.8% | 0.600 | 0.3 |       27 | 42.9% |  60.0% | 2.3× | 18.2% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 0.0% | 0.012 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.038 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |   97.3 | 0.0% | 0.005 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   80.0 | 0.0% | 0.009 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 0.0% | 0.600 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.596 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |   97.3 | 0.0% | 0.528 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   80.0 | 0.0% | 0.544 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available