# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-25 UTC
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
| DEGRADED |  101 |   95.4 | 29.7% | 0.649 | 0.3 |       97 | 6.7% |  11.8% | 0.4× | 35.0% |   0.1753 |
|      ALL |  197 |   59.1 | 35.0% | 0.685 | 0.5 |      193 | 20.3% |  32.6% | 0.9× | 36.7% |   0.2228 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  101 |   95.4 | 0.0% | 0.011 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0515 |
|      ALL |  197 |   59.1 | 1.0% | 0.020 | 0.0 |      193 | 50.0% |   6.7% | 6.4× | 0.6% |   0.0777 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  101 |   95.4 | 0.0% | 0.508 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0103 |
|      ALL |  197 |   59.1 | 0.5% | 0.553 | 0.0 |      193 | 0.0% |   0.0% |    - | 0.5% |   0.0259 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.5 | 37.5% | 0.627 | 0.4 |        8 | 33.3% | 100.0% | 2.7× | 28.6% |   0.1250 |
|       OK |    4 |   38.9 | 50.0% | 0.686 | 0.5 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   18 |   95.4 | 5.6% | 0.499 | 0.1 |       14 | 0.0% |   0.0% |    - | 8.3% |   0.1429 |
|      ALL |   30 |   66.3 | 20.0% | 0.558 | 0.2 |       26 | 16.7% |  33.3% | 1.4× | 21.7% |   0.1154 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.5 | 0.0% | 0.001 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.002 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   95.4 | 0.0% | 0.000 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   66.3 | 0.0% | 0.001 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.5 | 0.0% | 0.571 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.557 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   18 |   95.4 | 0.0% | 0.527 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   66.3 | 0.0% | 0.542 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available