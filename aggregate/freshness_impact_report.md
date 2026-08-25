# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 38.4% HIGHER than DEGRADED (3.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.9%) is 3.2× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.9%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   13.5 | 40.4% | 0.733 | 0.8 |       50 | 42.1% |  42.1% | 1.1× | 35.5% |   0.3800 |
|       OK |   32 |   32.3 | 40.6% | 0.734 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   83 |   95.4 | 34.9% | 0.681 | 0.4 |       81 | 3.7% |   7.1% | 0.2× | 38.8% |   0.1728 |
|      ALL |  167 |   57.8 | 37.7% | 0.708 | 0.6 |      163 | 18.6% |  28.9% | 0.8× | 38.4% |   0.2331 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   13.5 | 3.9% | 0.045 | 0.0 |       50 | 50.0% |  12.5% | 3.1× | 2.4% |   0.1600 |
|       OK |   32 |   32.3 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.013 | 0.0 |       81 |    - |   0.0% |    - | 0.0% |   0.0617 |
|      ALL |  167 |   57.8 | 1.2% | 0.023 | 0.0 |      163 | 50.0% |   7.1% | 5.8× | 0.7% |   0.0859 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   52 |   13.5 | 1.9% | 0.634 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.2% |   0.0800 |
|       OK |   32 |   32.3 | 0.0% | 0.557 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.504 | 0.0 |       81 |    - |   0.0% |    - | 0.0% |   0.0123 |
|      ALL |  167 |   57.8 | 0.6% | 0.555 | 0.0 |      163 | 0.0% |   0.0% |    - | 0.6% |   0.0307 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.1 | 33.3% | 0.714 | 0.5 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 33.3% | 0.755 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   17 |   99.9 | 29.4% | 0.694 | 0.4 |       15 | 33.3% |  25.0% | 1.2× | 18.2% |   0.2667 |
|      ALL |   29 |   68.0 | 31.0% | 0.711 | 0.4 |       25 | 20.0% |  25.0% | 1.2× | 19.1% |   0.1600 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.1 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 0.0% | 0.016 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   99.9 | 0.0% | 0.013 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   29 |   68.0 | 0.0% | 0.012 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.1 | 0.0% | 0.557 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 0.0% | 0.523 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   99.9 | 0.0% | 0.549 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   68.0 | 0.0% | 0.545 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available