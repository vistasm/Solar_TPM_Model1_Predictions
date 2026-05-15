# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-15 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (28.6%) is 28.6% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 33.3% | 0.718 | 0.5 |       21 | 28.6% |  22.2% | 0.7× | 41.7% |   0.4286 |
|       OK |   14 |   34.6 | 42.9% | 0.743 | 0.9 |       13 | 20.0% |  33.3% | 0.9× | 40.0% |   0.2308 |
| DEGRADED |   32 |  109.8 | 37.5% | 0.693 | 0.4 |       29 | 0.0% |   0.0% |    - | 44.0% |   0.1379 |
|      ALL |   67 |   64.1 | 37.3% | 0.711 | 0.5 |       63 | 13.0% |  18.8% | 0.5× | 42.5% |   0.2540 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.031 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   14 |   34.6 | 0.0% | 0.010 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
| DEGRADED |   32 |  109.8 | 0.0% | 0.004 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0690 |
|      ALL |   67 |   64.1 | 0.0% | 0.014 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0952 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   21 |   14.3 | 0.0% | 0.605 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0952 |
|       OK |   14 |   34.6 | 0.0% | 0.556 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   32 |  109.8 | 0.0% | 0.468 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.0345 |
|      ALL |   67 |   64.1 | 0.0% | 0.529 | 0.0 |       63 |    - |   0.0% |    - | 0.0% |   0.0476 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 85.7% | 0.899 | 1.3 |        7 | 16.7% |  50.0% | 0.6× | 100.0% |   0.2857 |
|       OK |    5 |   30.5 | 40.0% | 0.746 | 1.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   19 |  141.1 | 21.1% | 0.653 | 0.2 |       16 | 0.0% |   0.0% |    - | 23.1% |   0.1875 |
|      ALL |   31 |   94.3 | 38.7% | 0.723 | 0.6 |       27 | 20.0% |  33.3% | 0.9× | 38.1% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.077 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   30.5 | 0.0% | 0.014 | 0.0 |        4 |    - |   0.0% |    - | 0.0% |   0.2500 |
| DEGRADED |   19 |  141.1 | 0.0% | 0.006 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   94.3 | 0.0% | 0.023 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1481 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    7 |   12.8 | 0.0% | 0.740 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    5 |   30.5 | 0.0% | 0.608 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   19 |  141.1 | 0.0% | 0.483 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   94.3 | 0.0% | 0.561 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available