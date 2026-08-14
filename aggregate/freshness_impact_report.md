# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-14 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (42.1%) is 42.1% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (4.1%) is 3.2× the overall rate (1.3%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (2.0%) is 3.2× the overall rate (0.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 38.8% | 0.727 | 0.8 |       48 | 42.1% |  42.1% | 1.1× | 37.9% |   0.3958 |
|       OK |   30 |   32.4 | 43.3% | 0.740 | 0.7 |       29 | 16.7% |  40.0% | 1.0× | 41.7% |   0.1724 |
| DEGRADED |   78 |   99.3 | 32.0% | 0.670 | 0.3 |       76 | 0.0% |   0.0% |    - | 39.1% |   0.1579 |
|      ALL |  157 |   59.8 | 36.3% | 0.701 | 0.5 |      153 | 17.9% |  27.8% | 0.8× | 39.3% |   0.2353 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 4.1% | 0.047 | 0.0 |       48 | 50.0% |  12.5% | 3.0× | 2.5% |   0.1667 |
|       OK |   30 |   32.4 | 0.0% | 0.013 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
| DEGRADED |   78 |   99.3 | 0.0% | 0.011 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0526 |
|      ALL |  157 |   59.8 | 1.3% | 0.023 | 0.0 |      153 | 50.0% |   7.7% | 5.9× | 0.7% |   0.0850 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   49 |   13.6 | 2.0% | 0.637 | 0.0 |       48 | 0.0% |   0.0% |    - | 2.3% |   0.0833 |
|       OK |   30 |   32.4 | 0.0% | 0.556 | 0.0 |       29 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   78 |   99.3 | 0.0% | 0.499 | 0.0 |       76 |    - |   0.0% |    - | 0.0% |   0.0132 |
|      ALL |  157 |   59.8 | 0.6% | 0.553 | 0.0 |      153 | 0.0% |   0.0% |    - | 0.7% |   0.0327 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.9 | 40.0% | 0.695 | 0.4 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
|       OK |    6 |   27.1 | 66.7% | 0.849 | 0.7 |        5 | 0.0% |      - |    - | 60.0% |   0.0000 |
| DEGRADED |   19 |  106.8 | 10.5% | 0.572 | 0.1 |       17 | 0.0% |   0.0% |    - | 13.3% |   0.1176 |
|      ALL |   30 |   75.5 | 26.7% | 0.648 | 0.3 |       26 | 0.0% |   0.0% |    - | 29.2% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.9 | 0.0% | 0.005 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   27.1 | 0.0% | 0.030 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  106.8 | 0.0% | 0.002 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   75.5 | 0.0% | 0.008 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   14.9 | 0.0% | 0.518 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   27.1 | 0.0% | 0.514 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  106.8 | 0.0% | 0.486 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   75.5 | 0.0% | 0.497 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available