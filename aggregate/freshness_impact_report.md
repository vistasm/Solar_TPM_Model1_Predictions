# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-28 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.4 | 12.5% | 0.680 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    7 |   37.3 | 42.9% | 0.742 | 0.7 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
| DEGRADED |    4 |   86.3 | 50.0% | 0.682 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   19 |   38.8 | 31.6% | 0.703 | 0.5 |       15 | 0.0% |   0.0% |    - | 40.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.4 | 0.0% | 0.011 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.009 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.3 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   38.8 | 0.0% | 0.008 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.4 | 0.0% | 0.462 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.499 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.3 | 0.0% | 0.458 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   38.8 | 0.0% | 0.475 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.4 | 12.5% | 0.680 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    7 |   37.3 | 42.9% | 0.742 | 0.7 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
| DEGRADED |    4 |   86.3 | 50.0% | 0.682 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   19 |   38.8 | 31.6% | 0.703 | 0.5 |       15 | 0.0% |   0.0% |    - | 40.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.4 | 0.0% | 0.011 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.009 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.3 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   38.8 | 0.0% | 0.008 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   16.4 | 0.0% | 0.462 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    7 |   37.3 | 0.0% | 0.499 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    4 |   86.3 | 0.0% | 0.458 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   38.8 | 0.0% | 0.475 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available