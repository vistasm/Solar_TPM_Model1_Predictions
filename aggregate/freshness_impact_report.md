# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-31 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.2%) is 3.0× the overall rate (1.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.1%) is 3.0× the overall rate (0.7%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 39.6% | 0.733 | 0.8 |       47 | 42.1% |  42.1% | 1.0× | 39.3% |   0.4043 |
|       OK |   28 |   32.0 | 39.3% | 0.728 | 0.6 |       26 | 18.2% |  40.0% | 0.9× | 42.9% |   0.1923 |
| DEGRADED |   68 |   93.2 | 35.3% | 0.677 | 0.4 |       67 | 0.0% |   0.0% |    - | 42.9% |   0.1642 |
|      ALL |  144 |   54.7 | 37.5% | 0.706 | 0.6 |      140 | 18.5% |  28.6% | 0.7× | 41.9% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 4.2% | 0.048 | 0.0 |       47 | 50.0% |  12.5% | 2.9× | 2.6% |   0.1702 |
|       OK |   28 |   32.0 | 0.0% | 0.013 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
| DEGRADED |   68 |   93.2 | 0.0% | 0.013 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0597 |
|      ALL |  144 |   54.7 | 1.4% | 0.024 | 0.0 |      140 | 50.0% |   7.7% | 5.4× | 0.8% |   0.0929 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   48 |   13.5 | 2.1% | 0.640 | 0.0 |       47 | 0.0% |   0.0% |    - | 2.3% |   0.0851 |
|       OK |   28 |   32.0 | 0.0% | 0.555 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   68 |   93.2 | 0.0% | 0.494 | 0.0 |       67 |    - |   0.0% |    - | 0.0% |   0.0149 |
|      ALL |  144 |   54.7 | 0.7% | 0.555 | 0.0 |      140 | 0.0% |   0.0% |    - | 0.7% |   0.0357 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.1 | 53.3% | 0.819 | 1.5 |       14 | 62.5% |  83.3% | 1.5× | 37.5% |   0.4286 |
|       OK |    7 |   22.9 | 42.9% | 0.796 | 0.6 |        5 | 33.3% |  50.0% | 0.8× | 66.7% |   0.4000 |
| DEGRADED |    9 |   68.9 | 11.1% | 0.512 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|      ALL |   31 |   31.0 | 38.7% | 0.725 | 0.9 |       27 | 50.0% |  66.7% | 1.5× | 33.3% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.1 | 13.3% | 0.105 | 0.1 |       14 | 50.0% |  33.3% | 2.3× | 9.1% |   0.2143 |
|       OK |    7 |   22.9 | 0.0% | 0.022 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   68.9 | 0.0% | 0.001 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.0 | 6.5% | 0.056 | 0.1 |       27 | 50.0% |  33.3% | 4.5× | 4.2% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   15 |   12.1 | 6.7% | 0.720 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
|       OK |    7 |   22.9 | 0.0% | 0.516 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   68.9 | 0.0% | 0.437 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   31.0 | 3.2% | 0.592 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available