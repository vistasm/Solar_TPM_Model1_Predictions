# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-28 UTC
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
| DEGRADED |  104 |   97.8 | 28.8% | 0.641 | 0.3 |      100 | 6.7% |  11.8% | 0.4× | 33.7% |   0.1700 |
|      ALL |  200 |   60.9 | 34.5% | 0.680 | 0.5 |      196 | 20.3% |  32.6% | 0.9× | 35.9% |   0.2194 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  104 |   97.8 | 0.0% | 0.010 | 0.0 |      100 |    - |   0.0% |    - | 0.0% |   0.0500 |
|      ALL |  200 |   60.9 | 1.0% | 0.019 | 0.0 |      196 | 50.0% |   6.7% | 6.5× | 0.5% |   0.0765 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  104 |   97.8 | 0.0% | 0.508 | 0.0 |      100 |    - |   0.0% |    - | 0.0% |   0.0100 |
|      ALL |  200 |   60.9 | 0.5% | 0.552 | 0.0 |      196 | 0.0% |   0.0% |    - | 0.5% |   0.0255 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   15.2 | 16.7% | 0.532 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|       OK |    3 |   41.1 | 33.3% | 0.624 | 0.3 |        3 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   21 |  107.4 | 4.8% | 0.482 | 0.1 |       17 | 0.0% |   0.0% |    - | 6.7% |   0.1176 |
|      ALL |   30 |   82.4 | 10.0% | 0.506 | 0.1 |       26 | 0.0% |   0.0% |    - | 12.5% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   15.2 | 0.0% | 0.000 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   41.1 | 0.0% | 0.000 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  107.4 | 0.0% | 0.000 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   82.4 | 0.0% | 0.000 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   15.2 | 0.0% | 0.541 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   41.1 | 0.0% | 0.532 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   21 |  107.4 | 0.0% | 0.522 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   82.4 | 0.0% | 0.527 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available