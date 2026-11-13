# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (38.5%) is 28.7% HIGHER than DEGRADED (9.8%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.1%) is 3.9× the overall rate (0.8%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.6%) is 3.9× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 40.6% | 0.725 | 0.7 |       63 | 38.5% |  45.5% | 1.1× | 39.0% |   0.3492 |
|       OK |   39 |   33.1 | 43.6% | 0.736 | 0.6 |       37 | 18.8% |  50.0% | 1.2× | 41.9% |   0.1622 |
| DEGRADED |  146 |  102.0 | 28.8% | 0.632 | 0.3 |      145 | 9.8% |  17.4% | 0.6× | 30.3% |   0.1586 |
|      ALL |  249 |   68.4 | 34.1% | 0.672 | 0.5 |      245 | 20.5% |  33.3% | 1.0× | 34.0% |   0.2082 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 3.1% | 0.037 | 0.0 |       63 | 50.0% |  11.1% | 3.5× | 1.8% |   0.1429 |
|       OK |   39 |   33.1 | 0.0% | 0.015 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0270 |
| DEGRADED |  146 |  102.0 | 0.0% | 0.013 | 0.0 |      145 |    - |   0.0% |    - | 0.0% |   0.0483 |
|      ALL |  249 |   68.4 | 0.8% | 0.019 | 0.0 |      245 | 50.0% |   5.9% | 7.2× | 0.4% |   0.0694 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   64 |   13.4 | 1.6% | 0.624 | 0.0 |       63 | 0.0% |   0.0% |    - | 1.7% |   0.0635 |
|       OK |   39 |   33.1 | 0.0% | 0.560 | 0.0 |       37 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  146 |  102.0 | 0.0% | 0.521 | 0.0 |      145 |    - |   0.0% |    - | 0.0% |   0.0069 |
|      ALL |  249 |   68.4 | 0.4% | 0.553 | 0.0 |      245 | 0.0% |   0.0% |    - | 0.4% |   0.0204 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 50.0% | 0.818 | 0.5 |        3 | 0.0% |   0.0% |    - | 100.0% |   0.3333 |
|       OK |    3 |   34.4 | 66.7% | 0.819 | 1.0 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   24 |  112.4 | 16.7% | 0.572 | 0.2 |       23 | 33.3% |  33.3% | 2.6× | 10.0% |   0.1304 |
|      ALL |   31 |   91.7 | 25.8% | 0.627 | 0.3 |       27 | 33.3% |  40.0% | 1.8× | 18.2% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 0.0% | 0.012 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.038 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  112.4 | 0.0% | 0.028 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   91.7 | 0.0% | 0.027 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.6 | 0.0% | 0.600 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    3 |   34.4 | 0.0% | 0.596 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  112.4 | 0.0% | 0.541 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   91.7 | 0.0% | 0.554 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available