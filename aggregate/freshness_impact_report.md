# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-06 UTC
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
|    FRESH |   28 |   14.3 | 32.1% | 0.707 | 0.5 |       25 | 25.0% |  20.0% | 0.6× | 40.0% |   0.4000 |
|       OK |   18 |   35.7 | 44.4% | 0.726 | 0.8 |       17 | 14.3% |  33.3% | 0.8× | 42.9% |   0.1765 |
| DEGRADED |   43 |  103.1 | 39.5% | 0.707 | 0.4 |       43 | 0.0% |   0.0% |    - | 47.2% |   0.1628 |
|      ALL |   89 |   61.5 | 38.2% | 0.711 | 0.5 |       85 | 9.4% |  15.0% | 0.4× | 44.6% |   0.2353 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   14.3 | 0.0% | 0.025 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1200 |
|       OK |   18 |   35.7 | 0.0% | 0.008 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.0588 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.004 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |   89 |   61.5 | 0.0% | 0.011 | 0.0 |       85 |    - |   0.0% |    - | 0.0% |   0.0824 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   28 |   14.3 | 0.0% | 0.605 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.0800 |
|       OK |   18 |   35.7 | 0.0% | 0.564 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   43 |  103.1 | 0.0% | 0.493 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |   89 |   61.5 | 0.0% | 0.543 | 0.0 |       85 |    - |   0.0% |    - | 0.0% |   0.0353 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.4 | 37.5% | 0.703 | 0.8 |        5 | 0.0% |   0.0% |    - | 50.0% |   0.2000 |
|       OK |    6 |   39.6 | 50.0% | 0.670 | 0.7 |        5 | 0.0% |      - |    - | 40.0% |   0.0000 |
| DEGRADED |   17 |   74.3 | 35.3% | 0.716 | 0.3 |       17 | 0.0% |   0.0% |    - | 50.0% |   0.2941 |
|      ALL |   31 |   52.1 | 38.7% | 0.704 | 0.5 |       27 | 0.0% |   0.0% |    - | 47.6% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.4 | 0.0% | 0.053 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   39.6 | 0.0% | 0.003 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   74.3 | 0.0% | 0.001 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |
|      ALL |   31 |   52.1 | 0.0% | 0.015 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   14.4 | 0.0% | 0.603 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    6 |   39.6 | 0.0% | 0.581 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   74.3 | 0.0% | 0.563 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.1 | 0.0% | 0.577 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available