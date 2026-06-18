# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-18 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (20.0%) is 20.0% HIGHER than DEGRADED (0.0%) — fresher data is helping

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 31.2% | 0.690 | 0.5 |       32 | 20.0% |  16.7% | 0.5× | 40.0% |   0.3750 |
|       OK |   21 |   35.0 | 38.1% | 0.705 | 0.7 |       21 | 12.5% |  33.3% | 0.9× | 38.9% |   0.1429 |
| DEGRADED |   48 |  100.1 | 37.5% | 0.700 | 0.4 |       44 | 0.0% |   0.0% |    - | 48.6% |   0.1591 |
|      ALL |  101 |   59.4 | 35.6% | 0.698 | 0.5 |       97 | 8.3% |  13.6% | 0.4× | 44.0% |   0.2268 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.022 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   48 |  100.1 | 0.0% | 0.004 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0682 |
|      ALL |  101 |   59.4 | 0.0% | 0.011 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0825 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.600 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0938 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   48 |  100.1 | 0.0% | 0.484 | 0.0 |       44 |    - |   0.0% |    - | 0.0% |   0.0227 |
|      ALL |  101 |   59.4 | 0.0% | 0.538 | 0.0 |       97 |    - |   0.0% |    - | 0.0% |   0.0412 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.0 | 22.2% | 0.609 | 0.3 |        9 | 0.0% |   0.0% |    - | 28.6% |   0.2222 |
|       OK |    6 |   37.3 | 33.3% | 0.663 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   16 |   80.8 | 37.5% | 0.713 | 0.4 |       12 | 0.0% |   0.0% |    - | 66.7% |   0.2500 |
|      ALL |   31 |   53.6 | 32.3% | 0.673 | 0.3 |       27 | 0.0% |   0.0% |    - | 45.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.0 | 0.0% | 0.005 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    6 |   37.3 | 0.0% | 0.010 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.8 | 0.0% | 0.002 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   53.6 | 0.0% | 0.004 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   16.0 | 0.0% | 0.599 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    6 |   37.3 | 0.0% | 0.604 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |   80.8 | 0.0% | 0.516 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   53.6 | 0.0% | 0.557 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available