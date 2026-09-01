# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-01 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (43.5%) is 36.6% HIGHER than DEGRADED (6.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 3.2× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.8%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 42.6% | 0.740 | 0.8 |       54 | 43.5% |  47.6% | 1.1× | 39.4% |   0.3889 |
|       OK |   33 |   32.2 | 42.4% | 0.739 | 0.6 |       33 | 14.3% |  40.0% | 0.9× | 42.9% |   0.1515 |
| DEGRADED |   87 |   93.2 | 33.3% | 0.674 | 0.4 |       83 | 6.9% |  13.3% | 0.4× | 39.7% |   0.1807 |
|      ALL |  174 |   56.9 | 37.9% | 0.707 | 0.6 |      170 | 21.2% |  34.2% | 0.9× | 40.3% |   0.2412 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 3.7% | 0.043 | 0.0 |       54 | 50.0% |  11.1% | 3.0× | 2.2% |   0.1667 |
|       OK |   33 |   32.2 | 0.0% | 0.014 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0303 |
| DEGRADED |   87 |   93.2 | 0.0% | 0.012 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0602 |
|      ALL |  174 |   56.9 | 1.1% | 0.022 | 0.0 |      170 | 50.0% |   6.7% | 5.7× | 0.7% |   0.0882 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 1.8% | 0.635 | 0.0 |       54 | 0.0% |   0.0% |    - | 2.0% |   0.0741 |
|       OK |   33 |   32.2 | 0.0% | 0.559 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   87 |   93.2 | 0.0% | 0.507 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0120 |
|      ALL |  174 |   56.9 | 0.6% | 0.557 | 0.0 |      170 | 0.0% |   0.0% |    - | 0.6% |   0.0294 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   12.7 | 66.7% | 0.789 | 0.8 |        6 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
|       OK |    4 |   33.1 | 50.0% | 0.790 | 0.5 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   19 |   93.3 | 26.3% | 0.665 | 0.4 |       15 | 40.0% |  66.7% | 2.0× | 25.0% |   0.2000 |
|      ALL |   29 |   68.3 | 37.9% | 0.708 | 0.5 |       25 | 36.4% |  80.0% | 1.8× | 35.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   12.7 | 0.0% | 0.003 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    4 |   33.1 | 0.0% | 0.015 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   93.3 | 0.0% | 0.012 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   29 |   68.3 | 0.0% | 0.011 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   12.7 | 0.0% | 0.599 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   33.1 | 0.0% | 0.586 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   93.3 | 0.0% | 0.551 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   68.3 | 0.0% | 0.566 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available