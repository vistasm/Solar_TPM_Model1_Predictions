# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-12 UTC
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
|       OK |   20 |   34.5 | 40.0% | 0.722 | 0.7 |       19 | 12.5% |  33.3% | 0.8× | 43.8% |   0.1579 |
| DEGRADED |   44 |  102.2 | 40.9% | 0.713 | 0.4 |       43 | 0.0% |   0.0% |    - | 47.2% |   0.1628 |
|      ALL |   95 |   59.3 | 37.9% | 0.712 | 0.5 |       91 | 8.8% |  13.6% | 0.4× | 44.9% |   0.2418 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   14.4 | 0.0% | 0.022 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   20 |   34.5 | 0.0% | 0.010 | 0.0 |       19 |    - |   0.0% |    - | 0.0% |   0.0526 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.004 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |   95 |   59.3 | 0.0% | 0.011 | 0.0 |       91 |    - |   0.0% |    - | 0.0% |   0.0879 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   31 |   14.4 | 0.0% | 0.608 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1034 |
|       OK |   20 |   34.5 | 0.0% | 0.571 | 0.0 |       19 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.495 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |   95 |   59.3 | 0.0% | 0.548 | 0.0 |       91 |    - |   0.0% |    - | 0.0% |   0.0440 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 30.0% | 0.678 | 0.5 |        8 | 0.0% |   0.0% |    - | 40.0% |   0.3750 |
|       OK |    6 |   34.1 | 33.3% | 0.672 | 0.3 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 46.7% | 0.767 | 0.5 |       14 | 0.0% |   0.0% |    - | 54.5% |   0.2143 |
|      ALL |   31 |   49.2 | 38.7% | 0.720 | 0.5 |       27 | 0.0% |   0.0% |    - | 47.6% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.005 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   34.1 | 0.0% | 0.010 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 0.0% | 0.002 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   49.2 | 0.0% | 0.005 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.7 | 0.0% | 0.615 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   34.1 | 0.0% | 0.606 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 0.0% | 0.568 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.2 | 0.0% | 0.591 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available