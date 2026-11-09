# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 31.9% HIGHER than DEGRADED (9.8%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.2%) is 3.9× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.6%) is 3.9× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   13.5 | 41.3% | 0.725 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   37 |   33.1 | 43.2% | 0.732 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  145 |  102.3 | 28.3% | 0.631 | 0.3 |      145 | 9.8% |  17.4% | 0.6× | 30.3% |   0.1586 |
|      ALL |  245 |   69.0 | 33.9% | 0.670 | 0.5 |      241 | 20.0% |  32.6% | 1.0× | 33.3% |   0.2033 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   13.5 | 3.2% | 0.038 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   37 |   33.1 | 0.0% | 0.014 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  145 |  102.3 | 0.0% | 0.013 | 0.0 |      145 |    - |   0.0% |    - | 0.0% |   0.0483 |
|      ALL |  245 |   69.0 | 0.8% | 0.020 | 0.0 |      241 | 50.0% |   5.9% | 7.1× | 0.4% |   0.0705 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   63 |   13.5 | 1.6% | 0.625 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   37 |   33.1 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  145 |  102.3 | 0.0% | 0.520 | 0.0 |      145 |    - |   0.0% |    - | 0.0% |   0.0069 |
|      ALL |  245 |   69.0 | 0.4% | 0.553 | 0.0 |      241 | 0.0% |   0.0% |    - | 0.4% |   0.0207 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   11.3 | 66.7% | 0.846 | 0.7 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.3 | 100.0% | 0.846 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   27 |  111.9 | 25.9% | 0.616 | 0.4 |       27 | 28.6% |  50.0% | 1.9× | 21.7% |   0.1481 |
|      ALL |   31 |   99.7 | 32.3% | 0.645 | 0.4 |       27 | 28.6% |  50.0% | 1.9× | 21.7% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   11.3 | 0.0% | 0.015 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.3 | 0.0% | 0.073 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   27 |  111.9 | 0.0% | 0.026 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   31 |   99.7 | 0.0% | 0.026 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   11.3 | 0.0% | 0.608 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.3 | 0.0% | 0.588 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   27 |  111.9 | 0.0% | 0.556 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   99.7 | 0.0% | 0.562 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available