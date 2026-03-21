# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-21 UTC
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
|    FRESH |    6 |   17.1 | 0.0% | 0.646 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    4 |   38.5 | 50.0% | 0.754 | 1.0 |        3 | 0.0% |   0.0% |    - | 100.0% |   0.3333 |
| DEGRADED |    2 |   67.5 | 0.0% | 0.403 | 0.0 |        1 |    - |   0.0% |    - |   - |   1.0000 |
|      ALL |   12 |   32.6 | 16.7% | 0.641 | 0.3 |        8 | 0.0% |   0.0% |    - | 50.0% |   0.5000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   17.1 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.5 | 0.0% | 0.002 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    2 |   67.5 | 0.0% | 0.001 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   12 |   32.6 | 0.0% | 0.002 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   17.1 | 0.0% | 0.401 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.5 | 0.0% | 0.409 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    2 |   67.5 | 0.0% | 0.376 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   12 |   32.6 | 0.0% | 0.400 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   17.1 | 0.0% | 0.646 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.5000 |
|       OK |    4 |   38.5 | 50.0% | 0.754 | 1.0 |        3 | 0.0% |   0.0% |    - | 100.0% |   0.3333 |
| DEGRADED |    2 |   67.5 | 0.0% | 0.403 | 0.0 |        1 |    - |   0.0% |    - |   - |   1.0000 |
|      ALL |   12 |   32.6 | 16.7% | 0.641 | 0.3 |        8 | 0.0% |   0.0% |    - | 50.0% |   0.5000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   17.1 | 0.0% | 0.003 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.5 | 0.0% | 0.002 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    2 |   67.5 | 0.0% | 0.001 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   12 |   32.6 | 0.0% | 0.002 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   17.1 | 0.0% | 0.401 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.5 | 0.0% | 0.409 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    2 |   67.5 | 0.0% | 0.376 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   12 |   32.6 | 0.0% | 0.400 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available