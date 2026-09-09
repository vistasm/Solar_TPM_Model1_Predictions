# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.5%) is 3.1× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.1× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   13.5 | 41.4% | 0.732 | 0.8 |       55 | 41.7% |  47.6% | 1.1× | 41.2% |   0.3818 |
|       OK |   34 |   32.6 | 41.2% | 0.728 | 0.6 |       33 | 14.3% |  40.0% | 0.9× | 42.9% |   0.1515 |
| DEGRADED |   90 |   90.5 | 33.3% | 0.676 | 0.4 |       90 | 6.7% |  11.8% | 0.3× | 38.4% |   0.1889 |
|      ALL |  182 |   55.2 | 37.4% | 0.704 | 0.5 |      178 | 20.6% |  32.6% | 0.8× | 40.0% |   0.2416 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   13.5 | 3.5% | 0.040 | 0.0 |       55 | 50.0% |  11.1% | 3.1× | 2.2% |   0.1636 |
|       OK |   34 |   32.6 | 0.0% | 0.013 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.0303 |
| DEGRADED |   90 |   90.5 | 0.0% | 0.012 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |  182 |   55.2 | 1.1% | 0.021 | 0.0 |      178 | 50.0% |   6.7% | 5.9× | 0.6% |   0.0843 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   58 |   13.5 | 1.7% | 0.630 | 0.0 |       55 | 0.0% |   0.0% |    - | 2.0% |   0.0727 |
|       OK |   34 |   32.6 | 0.0% | 0.558 | 0.0 |       33 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   90 |   90.5 | 0.0% | 0.507 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0111 |
|      ALL |  182 |   55.2 | 0.5% | 0.556 | 0.0 |      178 | 0.0% |   0.0% |    - | 0.6% |   0.0281 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 50.0% | 0.725 | 0.6 |        7 | 40.0% | 100.0% | 1.4× | 60.0% |   0.2857 |
|       OK |    5 |   35.1 | 40.0% | 0.706 | 0.4 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   15 |   54.0 | 33.3% | 0.702 | 0.5 |       15 | 40.0% |  40.0% | 1.2× | 30.0% |   0.3333 |
|      ALL |   30 |   37.4 | 40.0% | 0.710 | 0.5 |       26 | 33.3% |  57.1% | 1.2× | 42.1% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 0.0% | 0.002 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   35.1 | 0.0% | 0.012 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   54.0 | 0.0% | 0.013 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   30 |   37.4 | 0.0% | 0.009 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.5 | 0.0% | 0.584 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   35.1 | 0.0% | 0.575 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   54.0 | 0.0% | 0.551 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   37.4 | 0.0% | 0.566 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available