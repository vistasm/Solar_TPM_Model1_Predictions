# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (40.0%) is 36.4% HIGHER than DEGRADED (3.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 3.1× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.8%) is 3.1× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 42.6% | 0.740 | 0.8 |       51 | 40.0% |  42.1% | 1.1× | 37.5% |   0.3725 |
|       OK |   32 |   32.3 | 40.6% | 0.734 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   83 |   95.4 | 34.9% | 0.681 | 0.4 |       82 | 3.6% |   7.1% | 0.2× | 39.7% |   0.1707 |
|      ALL |  169 |   57.3 | 38.5% | 0.710 | 0.6 |      165 | 18.0% |  28.9% | 0.8× | 39.4% |   0.2303 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 3.7% | 0.043 | 0.0 |       51 | 50.0% |  12.5% | 3.2× | 2.3% |   0.1569 |
|       OK |   32 |   32.3 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.013 | 0.0 |       82 |    - |   0.0% |    - | 0.0% |   0.0610 |
|      ALL |  169 |   57.3 | 1.2% | 0.023 | 0.0 |      165 | 50.0% |   7.1% | 5.9× | 0.7% |   0.0848 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 1.8% | 0.635 | 0.0 |       51 | 0.0% |   0.0% |    - | 2.1% |   0.0784 |
|       OK |   32 |   32.3 | 0.0% | 0.557 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.504 | 0.0 |       82 |    - |   0.0% |    - | 0.0% |   0.0122 |
|      ALL |  169 |   57.3 | 0.6% | 0.556 | 0.0 |      165 | 0.0% |   0.0% |    - | 0.6% |   0.0303 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 57.1% | 0.773 | 0.7 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|       OK |    6 |   32.6 | 33.3% | 0.755 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   16 |  102.3 | 31.2% | 0.699 | 0.4 |       15 | 25.0% |  33.3% | 1.2× | 25.0% |   0.2000 |
|      ALL |   29 |   66.2 | 37.9% | 0.729 | 0.5 |       25 | 14.3% |  33.3% | 1.2× | 27.3% |   0.1200 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 0.0% | 0.016 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  102.3 | 0.0% | 0.014 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   29 |   66.2 | 0.0% | 0.012 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.595 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   32.6 | 0.0% | 0.523 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  102.3 | 0.0% | 0.547 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.2 | 0.0% | 0.554 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available