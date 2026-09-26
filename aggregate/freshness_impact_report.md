# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.3× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.3× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  102 |   96.0 | 29.4% | 0.646 | 0.3 |       98 | 6.7% |  11.8% | 0.4× | 34.6% |   0.1735 |
|      ALL |  198 |   59.6 | 34.8% | 0.683 | 0.5 |      194 | 20.3% |  32.6% | 0.9× | 36.4% |   0.2216 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  102 |   96.0 | 0.0% | 0.011 | 0.0 |       98 |    - |   0.0% |    - | 0.0% |   0.0510 |
|      ALL |  198 |   59.6 | 1.0% | 0.019 | 0.0 |      194 | 50.0% |   6.7% | 6.5× | 0.6% |   0.0773 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  102 |   96.0 | 0.0% | 0.508 | 0.0 |       98 |    - |   0.0% |    - | 0.0% |   0.0102 |
|      ALL |  198 |   59.6 | 0.5% | 0.553 | 0.0 |      194 | 0.0% |   0.0% |    - | 0.5% |   0.0258 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.2 | 28.6% | 0.580 | 0.3 |        7 | 0.0% |      - |    - | 28.6% |   0.0000 |
|       OK |    4 |   38.9 | 50.0% | 0.686 | 0.5 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   19 |   98.6 | 5.3% | 0.494 | 0.1 |       15 | 0.0% |   0.0% |    - | 7.7% |   0.1333 |
|      ALL |   30 |   70.9 | 16.7% | 0.540 | 0.2 |       26 | 0.0% |   0.0% |    - | 20.8% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.2 | 0.0% | 0.000 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.002 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   98.6 | 0.0% | 0.000 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   70.9 | 0.0% | 0.001 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   14.2 | 0.0% | 0.555 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.557 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   98.6 | 0.0% | 0.526 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   70.9 | 0.0% | 0.537 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available