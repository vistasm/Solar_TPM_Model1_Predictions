# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-22 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (38.5%) is 26.8% HIGHER than DEGRADED (11.6%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.1%) is 3.9× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.5%) is 3.9× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   13.5 | 41.5% | 0.728 | 0.7 |       64 | 38.5% |  45.5% | 1.1× | 38.1% |   0.3438 |
|       OK |   39 |   33.1 | 43.6% | 0.736 | 0.6 |       39 | 17.6% |  50.0% | 1.1× | 42.4% |   0.1538 |
| DEGRADED |  154 |   98.3 | 27.9% | 0.629 | 0.3 |      151 | 11.6% |  20.0% | 0.7× | 30.2% |   0.1656 |
|      ALL |  258 |   67.1 | 33.7% | 0.670 | 0.5 |      254 | 20.9% |  34.0% | 1.0× | 33.8% |   0.2087 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   13.5 | 3.1% | 0.036 | 0.0 |       64 | 50.0% |  11.1% | 3.6× | 1.8% |   0.1406 |
|       OK |   39 |   33.1 | 0.0% | 0.015 | 0.0 |       39 |    - |   0.0% |    - | 0.0% |   0.0256 |
| DEGRADED |  154 |   98.3 | 0.0% | 0.013 | 0.0 |      151 |    - |   0.0% |    - | 0.0% |   0.0464 |
|      ALL |  258 |   67.1 | 0.8% | 0.019 | 0.0 |      254 | 50.0% |   5.9% | 7.5× | 0.4% |   0.0669 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   65 |   13.5 | 1.5% | 0.623 | 0.0 |       64 | 0.0% |   0.0% |    - | 1.7% |   0.0625 |
|       OK |   39 |   33.1 | 0.0% | 0.560 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  154 |   98.3 | 0.0% | 0.521 | 0.0 |      151 |    - |   0.0% |    - | 0.0% |   0.0066 |
|      ALL |  258 |   67.1 | 0.4% | 0.553 | 0.0 |      254 | 0.0% |   0.0% |    - | 0.4% |   0.0197 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   11.6 | 60.0% | 0.836 | 0.6 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|       OK |    3 |   34.4 | 66.7% | 0.819 | 1.0 |        3 | 50.0% | 100.0% | 1.5× | 50.0% |   0.3333 |
| DEGRADED |   23 |   90.5 | 13.0% | 0.513 | 0.1 |       20 | 33.3% |  33.3% | 2.2× | 11.8% |   0.1500 |
|      ALL |   31 |   72.3 | 25.8% | 0.595 | 0.3 |       27 | 28.6% |  40.0% | 1.5× | 22.7% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   11.6 | 0.0% | 0.010 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.038 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |   90.5 | 0.0% | 0.001 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.3 | 0.0% | 0.006 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    5 |   11.6 | 0.0% | 0.585 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.596 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   23 |   90.5 | 0.0% | 0.520 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   72.3 | 0.0% | 0.538 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available