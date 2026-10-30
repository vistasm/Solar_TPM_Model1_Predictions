# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 31.7% HIGHER than DEGRADED (10.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.9× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.9× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  137 |   99.5 | 29.2% | 0.643 | 0.3 |      136 | 10.0% |  18.2% | 0.6× | 31.6% |   0.1618 |
|      ALL |  233 |   67.1 | 33.9% | 0.676 | 0.5 |      232 | 20.2% |  33.3% | 1.0× | 34.2% |   0.2069 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  137 |   99.5 | 0.0% | 0.014 | 0.0 |      136 |    - |   0.0% |    - | 0.0% |   0.0515 |
|      ALL |  233 |   67.1 | 0.9% | 0.020 | 0.0 |      232 | 50.0% |   5.9% | 6.8× | 0.5% |   0.0733 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  137 |   99.5 | 0.0% | 0.521 | 0.0 |      136 |    - |   0.0% |    - | 0.0% |   0.0074 |
|      ALL |  233 |   67.1 | 0.4% | 0.554 | 0.0 |      232 | 0.0% |   0.0% |    - | 0.4% |   0.0216 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   29 |  101.5 | 34.5% | 0.654 | 0.5 |       28 | 20.0% |  40.0% | 1.1× | 34.8% |   0.1786 |
|      ALL |   29 |  101.5 | 34.5% | 0.654 | 0.5 |       28 | 20.0% |  40.0% | 1.1× | 34.8% |   0.1786 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   29 |  101.5 | 0.0% | 0.029 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   29 |  101.5 | 0.0% | 0.029 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.0714 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   29 |  101.5 | 0.0% | 0.567 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   29 |  101.5 | 0.0% | 0.567 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available