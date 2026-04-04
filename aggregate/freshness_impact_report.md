# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-04-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 7.7% | 0.641 | 0.1 |       10 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |    5 |   70.0 | 60.0% | 0.712 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   26 |   31.8 | 30.8% | 0.693 | 0.4 |       22 | 14.3% |  12.5% | 0.4× | 42.9% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.008 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   70.0 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.8 | 0.0% | 0.007 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.542 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   70.0 | 0.0% | 0.463 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.8 | 0.0% | 0.530 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 7.7% | 0.641 | 0.1 |       10 | 100.0% |  20.0% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   35.9 | 50.0% | 0.763 | 0.8 |        8 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
| DEGRADED |    5 |   70.0 | 60.0% | 0.712 | 0.8 |        4 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   26 |   31.8 | 30.8% | 0.693 | 0.4 |       22 | 14.3% |  12.5% | 0.4× | 42.9% |   0.3636 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.008 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.9 | 0.0% | 0.010 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   70.0 | 0.0% | 0.001 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.8 | 0.0% | 0.007 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   14.6 | 0.0% | 0.542 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   35.9 | 0.0% | 0.551 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    5 |   70.0 | 0.0% | 0.463 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   26 |   31.8 | 0.0% | 0.530 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.0455 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available