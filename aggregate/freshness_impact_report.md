# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (47.1%) is 47.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.7%) is 2.9× the overall rate (1.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.3%) is 2.9× the overall rate (0.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   43 |   13.3 | 39.5% | 0.732 | 0.8 |       39 | 47.1% |  44.4% | 1.0× | 42.9% |   0.4615 |
|       OK |   22 |   34.5 | 40.9% | 0.716 | 0.7 |       22 | 22.2% |  50.0% | 1.2× | 38.9% |   0.1818 |
| DEGRADED |   59 |   96.9 | 39.0% | 0.702 | 0.4 |       59 | 0.0% |   0.0% |    - | 46.9% |   0.1695 |
|      ALL |  124 |   56.8 | 39.5% | 0.715 | 0.6 |      120 | 20.4% |  31.2% | 0.8× | 44.3% |   0.2667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   43 |   13.3 | 4.7% | 0.053 | 0.1 |       39 | 50.0% |  12.5% | 2.4× | 3.2% |   0.2051 |
|       OK |   22 |   34.5 | 0.0% | 0.009 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.014 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0678 |
|      ALL |  124 |   56.8 | 1.6% | 0.027 | 0.0 |      120 | 50.0% |   7.7% | 4.6× | 0.9% |   0.1083 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   43 |   13.3 | 2.3% | 0.653 | 0.0 |       39 | 0.0% |   0.0% |    - | 2.9% |   0.1026 |
|       OK |   22 |   34.5 | 0.0% | 0.573 | 0.0 |       22 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   59 |   96.9 | 0.0% | 0.503 | 0.0 |       59 |    - |   0.0% |    - | 0.0% |   0.0169 |
|      ALL |  124 |   56.8 | 0.8% | 0.568 | 0.0 |      120 | 0.0% |   0.0% |    - | 0.9% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.1 | 53.8% | 0.782 | 1.6 |        9 | 85.7% | 100.0% | 1.3× | 33.3% |   0.6667 |
|       OK |    3 |   25.3 | 33.3% | 0.686 | 0.7 |        3 | 100.0% | 100.0% | 3.0× | 0.0% |   0.3333 |
| DEGRADED |   15 |   81.1 | 33.3% | 0.672 | 0.4 |       15 | 0.0% |   0.0% |    - | 41.7% |   0.2000 |
|      ALL |   31 |   46.4 | 41.9% | 0.719 | 0.9 |       27 | 53.8% |  70.0% | 1.4× | 35.3% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.1 | 15.4% | 0.121 | 0.1 |        9 | 50.0% |  25.0% | 1.1× | 20.0% |   0.4444 |
|       OK |    3 |   25.3 | 0.0% | 0.001 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   81.1 | 0.0% | 0.045 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   46.4 | 6.5% | 0.072 | 0.1 |       27 | 50.0% |  20.0% | 2.7× | 4.5% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   11.1 | 7.7% | 0.755 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    3 |   25.3 | 0.0% | 0.613 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   81.1 | 0.0% | 0.527 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   46.4 | 3.2% | 0.631 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available