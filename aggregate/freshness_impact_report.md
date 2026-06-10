# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-10 UTC
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
|    FRESH |   30 |   14.2 | 33.3% | 0.711 | 0.5 |       28 | 22.2% |  16.7% | 0.5× | 43.8% |   0.4286 |
|       OK |   19 |   36.0 | 42.1% | 0.721 | 0.7 |       18 | 12.5% |  33.3% | 0.8× | 46.7% |   0.1667 |
| DEGRADED |   44 |  102.2 | 40.9% | 0.713 | 0.4 |       43 | 0.0% |   0.0% |    - | 47.2% |   0.1628 |
|      ALL |   93 |   60.3 | 38.7% | 0.714 | 0.5 |       89 | 8.8% |  13.6% | 0.4× | 46.3% |   0.2472 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   14.2 | 0.0% | 0.023 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   19 |   36.0 | 0.0% | 0.011 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.004 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0698 |
|      ALL |   93 |   60.3 | 0.0% | 0.012 | 0.0 |       89 |    - |   0.0% |    - | 0.0% |   0.0899 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   14.2 | 0.0% | 0.608 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.1071 |
|       OK |   19 |   36.0 | 0.0% | 0.567 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   44 |  102.2 | 0.0% | 0.495 | 0.0 |       43 |    - |   0.0% |    - | 0.0% |   0.0233 |
|      ALL |   93 |   60.3 | 0.0% | 0.546 | 0.0 |       89 |    - |   0.0% |    - | 0.0% |   0.0449 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.2 | 40.0% | 0.715 | 0.7 |        8 | 0.0% |   0.0% |    - | 60.0% |   0.3750 |
|       OK |    6 |   39.8 | 50.0% | 0.693 | 0.7 |        5 | 0.0% |      - |    - | 60.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 46.7% | 0.767 | 0.5 |       14 | 0.0% |   0.0% |    - | 54.5% |   0.2143 |
|      ALL |   31 |   50.1 | 45.2% | 0.736 | 0.6 |       27 | 0.0% |   0.0% |    - | 57.1% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.2 | 0.0% | 0.043 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   39.8 | 0.0% | 0.011 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 0.0% | 0.002 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   50.1 | 0.0% | 0.017 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.2 | 0.0% | 0.613 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   39.8 | 0.0% | 0.597 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   78.2 | 0.0% | 0.568 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   50.1 | 0.0% | 0.588 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available