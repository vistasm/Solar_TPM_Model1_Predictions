# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (45.5%) is 38.6% HIGHER than DEGRADED (6.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 3.2× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.8%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 42.6% | 0.740 | 0.8 |       53 | 45.5% |  47.6% | 1.1× | 37.5% |   0.3962 |
|       OK |   33 |   32.2 | 42.4% | 0.739 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   85 |   94.8 | 34.1% | 0.680 | 0.4 |       83 | 6.9% |  13.3% | 0.4× | 39.7% |   0.1807 |
|      ALL |  172 |   57.2 | 38.4% | 0.710 | 0.6 |      168 | 21.9% |  34.2% | 0.9× | 39.4% |   0.2440 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 3.7% | 0.043 | 0.0 |       53 | 50.0% |  11.1% | 2.9× | 2.3% |   0.1698 |
|       OK |   33 |   32.2 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   85 |   94.8 | 0.0% | 0.013 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0602 |
|      ALL |  172 |   57.2 | 1.2% | 0.022 | 0.0 |      168 | 50.0% |   6.7% | 5.6× | 0.7% |   0.0893 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 1.8% | 0.635 | 0.0 |       53 | 0.0% |   0.0% |    - | 2.0% |   0.0755 |
|       OK |   33 |   32.2 | 0.0% | 0.559 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   85 |   94.8 | 0.0% | 0.506 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0120 |
|      ALL |  172 |   57.2 | 0.6% | 0.557 | 0.0 |      168 | 0.0% |   0.0% |    - | 0.6% |   0.0298 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 57.1% | 0.773 | 0.7 |        6 | 66.7% | 100.0% | 2.0× | 25.0% |   0.3333 |
|       OK |    5 |   33.9 | 60.0% | 0.798 | 0.6 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   17 |  101.0 | 29.4% | 0.691 | 0.4 |       15 | 40.0% |  66.7% | 2.0× | 25.0% |   0.2000 |
|      ALL |   29 |   68.1 | 41.4% | 0.729 | 0.5 |       25 | 40.0% |  80.0% | 2.0× | 30.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.003 | 0.0 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
|       OK |    5 |   33.9 | 0.0% | 0.020 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  101.0 | 0.0% | 0.013 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   29 |   68.1 | 0.0% | 0.012 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.595 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   33.9 | 0.0% | 0.582 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  101.0 | 0.0% | 0.553 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   68.1 | 0.0% | 0.568 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available