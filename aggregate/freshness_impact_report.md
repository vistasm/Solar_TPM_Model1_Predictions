# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (40.0%) is 33.1% HIGHER than DEGRADED (6.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 3.1× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.8%) is 3.1× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 42.6% | 0.740 | 0.8 |       51 | 40.0% |  42.1% | 1.1× | 37.5% |   0.3725 |
|       OK |   33 |   32.2 | 42.4% | 0.739 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   83 |   95.4 | 34.9% | 0.681 | 0.4 |       83 | 6.9% |  13.3% | 0.4× | 39.7% |   0.1807 |
|      ALL |  170 |   57.1 | 38.8% | 0.711 | 0.6 |      166 | 19.4% |  30.8% | 0.8× | 39.4% |   0.2349 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 3.7% | 0.043 | 0.0 |       51 | 50.0% |  12.5% | 3.2× | 2.3% |   0.1569 |
|       OK |   33 |   32.2 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.013 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0602 |
|      ALL |  170 |   57.1 | 1.2% | 0.023 | 0.0 |      166 | 50.0% |   7.1% | 5.9× | 0.7% |   0.0843 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 1.8% | 0.635 | 0.0 |       51 | 0.0% |   0.0% |    - | 2.1% |   0.0784 |
|       OK |   33 |   32.2 | 0.0% | 0.559 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   83 |   95.4 | 0.0% | 0.504 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0120 |
|      ALL |  170 |   57.1 | 0.6% | 0.557 | 0.0 |      166 | 0.0% |   0.0% |    - | 0.6% |   0.0301 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 57.1% | 0.773 | 0.7 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
|       OK |    6 |   33.4 | 50.0% | 0.769 | 0.5 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   16 |  102.3 | 31.2% | 0.699 | 0.4 |       16 | 40.0% |  50.0% | 1.6× | 25.0% |   0.2500 |
|      ALL |   29 |   66.4 | 41.4% | 0.731 | 0.5 |       25 | 25.0% |  50.0% | 1.6× | 28.6% |   0.1600 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.017 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  102.3 | 0.0% | 0.014 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   29 |   66.4 | 0.0% | 0.012 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0400 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.595 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   33.4 | 0.0% | 0.556 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  102.3 | 0.0% | 0.547 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   66.4 | 0.0% | 0.560 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available