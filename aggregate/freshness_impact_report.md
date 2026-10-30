# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.4× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.4× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  107 |  100.5 | 28.0% | 0.636 | 0.3 |      106 | 6.7% |  11.8% | 0.4× | 31.5% |   0.1604 |
|      ALL |  203 |   62.8 | 34.0% | 0.677 | 0.5 |      202 | 20.3% |  32.6% | 0.9× | 34.6% |   0.2129 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  107 |  100.5 | 0.0% | 0.010 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0472 |
|      ALL |  203 |   62.8 | 1.0% | 0.019 | 0.0 |      202 | 50.0% |   6.7% | 6.7× | 0.5% |   0.0743 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  107 |  100.5 | 0.0% | 0.508 | 0.0 |      106 |    - |   0.0% |    - | 0.0% |   0.0094 |
|      ALL |  203 |   62.8 | 0.5% | 0.551 | 0.0 |      202 | 0.0% |   0.0% |    - | 0.5% |   0.0248 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |  173.7 | 0.0% | 0.299 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |  173.7 | 0.0% | 0.299 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |  173.7 | 0.0% | 0.000 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |  173.7 | 0.0% | 0.000 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    2 |  173.7 | 0.0% | 0.485 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    2 |  173.7 | 0.0% | 0.485 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available