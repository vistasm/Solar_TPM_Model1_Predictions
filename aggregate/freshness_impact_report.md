# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.9%) is 36.0% HIGHER than DEGRADED (6.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.7%) is 3.2× the overall rate (1.2%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.8%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 42.6% | 0.740 | 0.8 |       52 | 42.9% |  45.0% | 1.1× | 37.5% |   0.3846 |
|       OK |   33 |   32.2 | 42.4% | 0.739 | 0.6 |       32 | 15.4% |  40.0% | 1.0× | 40.7% |   0.1562 |
| DEGRADED |   84 |   94.9 | 34.5% | 0.681 | 0.4 |       83 | 6.9% |  13.3% | 0.4× | 39.7% |   0.1807 |
|      ALL |  171 |   57.1 | 38.6% | 0.711 | 0.6 |      167 | 20.6% |  32.5% | 0.9× | 39.4% |   0.2395 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 3.7% | 0.043 | 0.0 |       52 | 50.0% |  11.1% | 2.9× | 2.3% |   0.1731 |
|       OK |   33 |   32.2 | 0.0% | 0.014 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
| DEGRADED |   84 |   94.9 | 0.0% | 0.013 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0602 |
|      ALL |  171 |   57.1 | 1.2% | 0.023 | 0.0 |      167 | 50.0% |   6.7% | 5.6× | 0.7% |   0.0898 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   54 |   13.4 | 1.8% | 0.635 | 0.0 |       52 | 0.0% |   0.0% |    - | 2.1% |   0.0769 |
|       OK |   33 |   32.2 | 0.0% | 0.559 | 0.0 |       32 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   84 |   94.9 | 0.0% | 0.505 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0120 |
|      ALL |  171 |   57.1 | 0.6% | 0.557 | 0.0 |      167 | 0.0% |   0.0% |    - | 0.6% |   0.0299 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 57.1% | 0.773 | 0.7 |        5 | 50.0% | 100.0% | 2.5× | 25.0% |   0.2000 |
|       OK |    5 |   33.9 | 60.0% | 0.798 | 0.6 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   17 |   99.6 | 29.4% | 0.699 | 0.4 |       16 | 40.0% |  50.0% | 1.6× | 25.0% |   0.2500 |
|      ALL |   29 |   67.3 | 41.4% | 0.734 | 0.5 |       25 | 33.3% |  60.0% | 1.7× | 30.0% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.003 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    5 |   33.9 | 0.0% | 0.020 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   99.6 | 0.0% | 0.013 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   29 |   67.3 | 0.0% | 0.012 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.7 | 0.0% | 0.595 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   33.9 | 0.0% | 0.582 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   99.6 | 0.0% | 0.549 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |   67.3 | 0.0% | 0.566 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available