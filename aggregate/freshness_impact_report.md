# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-29 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (25.0%) is 25.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 33.3% | 0.705 | 0.5 |       24 | 25.0% |  20.0% | 0.6× | 42.9% |   0.4167 |
|       OK |   16 |   34.6 | 37.5% | 0.700 | 0.8 |       16 | 16.7% |  33.3% | 0.9× | 38.5% |   0.1875 |
| DEGRADED |   41 |  104.1 | 41.5% | 0.713 | 0.4 |       37 | 0.0% |   0.0% |    - | 45.5% |   0.1081 |
|      ALL |   81 |   63.7 | 38.3% | 0.708 | 0.5 |       77 | 10.3% |  17.6% | 0.5× | 43.3% |   0.2208 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.027 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   16 |   34.6 | 0.0% | 0.009 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
| DEGRADED |   41 |  104.1 | 0.0% | 0.004 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0541 |
|      ALL |   81 |   63.7 | 0.0% | 0.012 | 0.0 |       77 |    - |   0.0% |    - | 0.0% |   0.0779 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   14.1 | 0.0% | 0.596 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |   16 |   34.6 | 0.0% | 0.551 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   41 |  104.1 | 0.0% | 0.490 | 0.0 |       37 |    - |   0.0% |    - | 0.0% |   0.0270 |
|      ALL |   81 |   63.7 | 0.0% | 0.534 | 0.0 |       77 |    - |   0.0% |    - | 0.0% |   0.0390 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.7 | 50.0% | 0.729 | 0.8 |        6 | 0.0% |   0.0% |    - | 75.0% |   0.3333 |
|       OK |    6 |   36.1 | 16.7% | 0.603 | 0.3 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
| DEGRADED |   19 |   68.7 | 42.1% | 0.741 | 0.4 |       15 | 0.0% |   0.0% |    - | 46.2% |   0.1333 |
|      ALL |   31 |   51.7 | 38.7% | 0.712 | 0.5 |       27 | 0.0% |   0.0% |    - | 43.5% |   0.1481 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.7 | 0.0% | 0.074 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.005 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   68.7 | 0.0% | 0.002 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |   31 |   51.7 | 0.0% | 0.017 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   13.7 | 0.0% | 0.586 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   36.1 | 0.0% | 0.536 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |   68.7 | 0.0% | 0.561 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   51.7 | 0.0% | 0.561 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available