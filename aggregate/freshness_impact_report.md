# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.3%) is 3.0× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.0× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   13.6 | 40.4% | 0.735 | 0.8 |       46 | 42.1% |  42.1% | 1.0× | 40.7% |   0.4130 |
|       OK |   27 |   32.0 | 40.7% | 0.732 | 0.7 |       26 | 18.2% |  40.0% | 0.9× | 42.9% |   0.1923 |
| DEGRADED |   67 |   93.7 | 35.8% | 0.677 | 0.4 |       65 | 0.0% |   0.0% |    - | 43.6% |   0.1538 |
|      ALL |  141 |   55.2 | 38.3% | 0.707 | 0.6 |      137 | 18.5% |  29.4% | 0.8× | 42.7% |   0.2482 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   13.6 | 4.3% | 0.049 | 0.0 |       46 | 50.0% |  12.5% | 2.9× | 2.6% |   0.1739 |
|       OK |   27 |   32.0 | 0.0% | 0.013 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
| DEGRADED |   67 |   93.7 | 0.0% | 0.013 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0615 |
|      ALL |  141 |   55.2 | 1.4% | 0.025 | 0.0 |      137 | 50.0% |   7.7% | 5.3× | 0.8% |   0.0949 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   47 |   13.6 | 2.1% | 0.641 | 0.0 |       46 | 0.0% |   0.0% |    - | 2.4% |   0.0870 |
|       OK |   27 |   32.0 | 0.0% | 0.560 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   67 |   93.7 | 0.0% | 0.494 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  141 |   55.2 | 0.7% | 0.556 | 0.0 |      137 | 0.0% |   0.0% |    - | 0.8% |   0.0365 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   11.6 | 60.0% | 0.829 | 1.5 |       14 | 66.7% |  85.7% | 1.3× | 42.9% |   0.5000 |
|       OK |    6 |   21.6 | 50.0% | 0.825 | 0.7 |        5 | 33.3% |  50.0% | 0.8× | 66.7% |   0.4000 |
| DEGRADED |   10 |   89.8 | 10.0% | 0.537 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   31 |   38.7 | 41.9% | 0.734 | 0.9 |       27 | 53.8% |  70.0% | 1.4× | 35.3% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   11.6 | 13.3% | 0.107 | 0.1 |       14 | 50.0% |  25.0% | 1.8× | 10.0% |   0.2857 |
|       OK |    6 |   21.6 | 0.0% | 0.025 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   89.8 | 0.0% | 0.034 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.7 | 6.5% | 0.068 | 0.1 |       27 | 50.0% |  25.0% | 3.4× | 4.3% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   11.6 | 6.7% | 0.731 | 0.1 |       14 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |
|       OK |    6 |   21.6 | 0.0% | 0.531 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   89.8 | 0.0% | 0.484 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   38.7 | 3.2% | 0.612 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available