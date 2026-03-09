# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-03-09 UTC
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
|    FRESH |    4 |   13.0 | 0.0% | 0.447 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 20.0% | 0.428 | 0.2 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   10 |   85.9 | 10.0% | 0.411 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   57.4 | 10.5% | 0.423 | 0.1 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   13.0 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   85.9 | 0.0% | 0.003 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   57.4 | 0.0% | 0.002 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   13.0 | 0.0% | 0.426 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 0.0% | 0.392 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   85.9 | 0.0% | 0.404 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   57.4 | 0.0% | 0.405 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   13.0 | 0.0% | 0.447 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 20.0% | 0.428 | 0.2 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   10 |   85.9 | 10.0% | 0.411 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   57.4 | 10.5% | 0.423 | 0.1 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   13.0 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   85.9 | 0.0% | 0.003 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   57.4 | 0.0% | 0.002 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   13.0 | 0.0% | 0.426 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 0.0% | 0.392 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   85.9 | 0.0% | 0.404 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   19 |   57.4 | 0.0% | 0.405 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available