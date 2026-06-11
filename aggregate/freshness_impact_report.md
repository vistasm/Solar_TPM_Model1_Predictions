# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-11 UTC
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
|    FRESH |   30 |   14.2 | 33.3% | 0.711 | 0.5 |       29 | 22.2% |  16.7% | 0.5× | 41.2% |   0.4138 |
|       OK |   20 |   34.5 | 40.0% | 0.722 | 0.7 |       18 | 12.5% |  33.3% | 0.8× | 46.7% |   0.1667 |
| DEGRADED |   44 |  102.2 | 40.9% | 0.713 | 0.4 |       43 | 0.0% |   0.0% |    - | 47.2% |   0.1628 |
|      ALL |   94 |   59.7 | 38.3% | 0.714 | 0.5 |       90 | 8.8% |  13.6% | 0.4× | 45.6% |   0.2444 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   14.2 | 0.0% | 0.023 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   20 |   34.5 | 0.0% | 0.010 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.004 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |   94 |   59.7 | 0.0% | 0.011 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   14.2 | 0.0% | 0.608 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1034 |
|       OK |   20 |   34.5 | 0.0% | 0.571 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.495 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |   94 |   59.7 | 0.0% | 0.547 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 33.3% | 0.693 | 0.6 |        8 | 0.0% |   0.0% |    - | 40.0% |   0.3750 |
|       OK |    7 |   34.9 | 42.9% | 0.698 | 0.6 |        5 | 0.0% |      - |    - | 60.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 46.7% | 0.767 | 0.5 |       14 | 0.0% |   0.0% |    - | 54.5% |   0.2143 |
|      ALL |   31 |   49.8 | 41.9% | 0.730 | 0.5 |       27 | 0.0% |   0.0% |    - | 52.4% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.005 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    7 |   34.9 | 0.0% | 0.010 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 0.0% | 0.002 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   49.8 | 0.0% | 0.005 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.0 | 0.0% | 0.615 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    7 |   34.9 | 0.0% | 0.604 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 0.0% | 0.568 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.8 | 0.0% | 0.590 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available