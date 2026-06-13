# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (22.2%) is 22.2% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   14.4 | 32.3% | 0.705 | 0.5 |       29 | 22.2% |  16.7% | 0.5× | 41.2% |   0.4138 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       19 | 12.5% |  33.3% | 0.8× | 43.8% |   0.1579 |
| DEGRADED |   44 |  102.2 | 40.9% | 0.713 | 0.4 |       44 | 0.0% |   0.0% |    - | 48.6% |   0.1591 |
|      ALL |   96 |   59.2 | 37.5% | 0.709 | 0.5 |       92 | 8.6% |  13.6% | 0.4× | 45.7% |   0.2391 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   14.4 | 0.0% | 0.022 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.004 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |   96 |   59.2 | 0.0% | 0.011 | 0.0 |       92 |    - |   0.0% |    - | 0.0% |   0.0870 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   14.4 | 0.0% | 0.608 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1034 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.495 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |
|      ALL |   96 |   59.2 | 0.0% | 0.547 | 0.0 |       92 |    - |   0.0% |    - | 0.0% |   0.0435 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 30.0% | 0.678 | 0.5 |        8 | 0.0% |   0.0% |    - | 40.0% |   0.3750 |
|       OK |    7 |   35.7 | 28.6% | 0.630 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   14 |   79.2 | 50.0% | 0.771 | 0.5 |       14 | 0.0% |   0.0% |    - | 63.6% |   0.2143 |
|      ALL |   31 |   48.6 | 38.7% | 0.709 | 0.5 |       27 | 0.0% |   0.0% |    - | 52.4% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.005 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    7 |   35.7 | 0.0% | 0.008 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   79.2 | 0.0% | 0.003 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   48.6 | 0.0% | 0.005 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.615 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    7 |   35.7 | 0.0% | 0.591 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   79.2 | 0.0% | 0.567 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   48.6 | 0.0% | 0.588 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available