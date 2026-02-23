# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-02-23 UTC
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
|    FRESH |    2 |   15.0 | 0.0% | 0.254 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   41.9 | 0.0% | 0.185 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |    3 |   63.6 | 0.0% | 0.322 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    6 |   43.8 | 0.0% | 0.277 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   15.0 | 0.0% | 0.000 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   41.9 | 0.0% | 0.001 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |    3 |   63.6 | 0.0% | 0.001 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    6 |   43.8 | 0.0% | 0.001 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   15.0 | 0.0% | 0.328 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   41.9 | 0.0% | 0.355 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |    3 |   63.6 | 0.0% | 0.300 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    6 |   43.8 | 0.0% | 0.319 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   15.0 | 0.0% | 0.254 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   41.9 | 0.0% | 0.185 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |    3 |   63.6 | 0.0% | 0.322 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    6 |   43.8 | 0.0% | 0.277 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   15.0 | 0.0% | 0.000 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   41.9 | 0.0% | 0.001 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |    3 |   63.6 | 0.0% | 0.001 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    6 |   43.8 | 0.0% | 0.001 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    2 |   15.0 | 0.0% | 0.328 | 0.0 |        0 |    - |      - |    - |   - |        - |
|       OK |    1 |   41.9 | 0.0% | 0.355 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |    3 |   63.6 | 0.0% | 0.300 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    6 |   43.8 | 0.0% | 0.319 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available