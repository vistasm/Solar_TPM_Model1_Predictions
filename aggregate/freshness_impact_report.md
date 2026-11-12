# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (40.0%) is 30.2% HIGHER than DEGRADED (9.8%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.1%) is 3.9× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.6%) is 3.9× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 40.6% | 0.725 | 0.7 |       62 | 40.0% |  45.5% | 1.1× | 37.5% |   0.3548 |
|       OK |   38 |   33.1 | 44.7% | 0.738 | 0.7 |       37 | 18.8% |  50.0% | 1.2× | 41.9% |   0.1622 |
| DEGRADED |  146 |  102.0 | 28.8% | 0.632 | 0.3 |      145 | 9.8% |  17.4% | 0.6× | 30.3% |   0.1586 |
|      ALL |  248 |   68.6 | 34.3% | 0.672 | 0.5 |      244 | 20.7% |  33.3% | 1.0× | 33.7% |   0.2090 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 3.1% | 0.037 | 0.0 |       62 | 50.0% |  11.1% | 3.4× | 1.9% |   0.1452 |
|       OK |   38 |   33.1 | 0.0% | 0.015 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0270 |
| DEGRADED |  146 |  102.0 | 0.0% | 0.013 | 0.0 |      145 |    - |   0.0% |    - | 0.0% |   0.0483 |
|      ALL |  248 |   68.6 | 0.8% | 0.020 | 0.0 |      244 | 50.0% |   5.9% | 7.2× | 0.4% |   0.0697 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 1.6% | 0.624 | 0.0 |       62 | 0.0% |   0.0% |    - | 1.7% |   0.0645 |
|       OK |   38 |   33.1 | 0.0% | 0.560 | 0.0 |       37 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  146 |  102.0 | 0.0% | 0.521 | 0.0 |      145 |    - |   0.0% |    - | 0.0% |   0.0069 |
|      ALL |  248 |   68.6 | 0.4% | 0.553 | 0.0 |      244 | 0.0% |   0.0% |    - | 0.4% |   0.0205 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 50.0% | 0.818 | 0.5 |        2 | 0.0% |   0.0% |    - | 100.0% |   0.5000 |
|       OK |    2 |   35.3 | 100.0% | 0.904 | 1.5 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   25 |  111.7 | 20.0% | 0.583 | 0.2 |       24 | 25.0% |  33.3% | 2.0× | 14.3% |   0.1250 |
|      ALL |   31 |   93.7 | 29.0% | 0.634 | 0.3 |       27 | 33.3% |  40.0% | 1.8× | 18.2% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 0.0% | 0.012 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.3 | 0.0% | 0.057 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  111.7 | 0.0% | 0.027 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.7 | 0.0% | 0.027 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 0.0% | 0.600 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.3 | 0.0% | 0.615 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  111.7 | 0.0% | 0.544 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.7 | 0.0% | 0.555 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available