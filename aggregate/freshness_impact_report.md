# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-08 UTC
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
|    FRESH |   62 |   13.5 | 40.3% | 0.722 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   37 |   33.1 | 43.2% | 0.732 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  145 |  102.3 | 28.3% | 0.631 | 0.3 |      144 | 9.8% |  18.2% | 0.6× | 30.3% |   0.1528 |
|      ALL |  244 |   69.2 | 33.6% | 0.669 | 0.5 |      240 | 20.0% |  33.3% | 1.0× | 33.3% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   13.5 | 3.2% | 0.038 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   37 |   33.1 | 0.0% | 0.014 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  145 |  102.3 | 0.0% | 0.013 | 0.0 |      144 |    - |   0.0% |    - | 0.0% |   0.0486 |
|      ALL |  244 |   69.2 | 0.8% | 0.020 | 0.0 |      240 | 50.0% |   5.9% | 7.1× | 0.4% |   0.0708 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   13.5 | 1.6% | 0.625 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   37 |   33.1 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  145 |  102.3 | 0.0% | 0.520 | 0.0 |      144 |    - |   0.0% |    - | 0.0% |   0.0069 |
|      ALL |  244 |   69.2 | 0.4% | 0.553 | 0.0 |      240 | 0.0% |   0.0% |    - | 0.4% |   0.0208 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   11.2 | 50.0% | 0.817 | 0.5 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.3 | 100.0% | 0.846 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  111.4 | 28.6% | 0.628 | 0.4 |       27 | 25.0% |  66.7% | 2.2× | 25.0% |   0.1111 |
|      ALL |   31 |  102.4 | 32.3% | 0.647 | 0.4 |       27 | 25.0% |  66.7% | 2.2× | 25.0% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   11.2 | 0.0% | 0.012 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.3 | 0.0% | 0.073 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  111.4 | 0.0% | 0.030 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   31 |  102.4 | 0.0% | 0.030 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   11.2 | 0.0% | 0.605 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   35.3 | 0.0% | 0.588 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   28 |  111.4 | 0.0% | 0.561 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |  102.4 | 0.0% | 0.565 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available