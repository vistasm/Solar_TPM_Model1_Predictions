# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-20 UTC
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
| DEGRADED |   50 |   98.9 | 36.0% | 0.684 | 0.4 |       46 | 0.0% |   0.0% |    - | 46.2% |   0.1522 |
|      ALL |  103 |   59.7 | 34.9% | 0.690 | 0.5 |       99 | 8.3% |  13.6% | 0.4× | 42.9% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.022 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |   21 |   35.0 | 0.0% | 0.010 | 0.0 |       21 |    - |   0.0% |    - | 0.0% |   0.0476 |
| DEGRADED |   50 |   98.9 | 0.0% | 0.004 | 0.0 |       46 |    - |   0.0% |    - | 0.0% |   0.0652 |
|      ALL |  103 |   59.7 | 0.0% | 0.011 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0808 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   32 |   14.5 | 0.0% | 0.600 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0938 |
|       OK |   21 |   35.0 | 0.0% | 0.568 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |   98.9 | 0.0% | 0.481 | 0.0 |       46 |    - |   0.0% |    - | 0.0% |   0.0217 |
|      ALL |  103 |   59.7 | 0.0% | 0.535 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0404 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 25.0% | 0.646 | 0.4 |        8 | 0.0% |   0.0% |    - | 33.3% |   0.2500 |
|       OK |    6 |   37.3 | 33.3% | 0.663 | 0.3 |        6 | 0.0% |      - |    - | 33.3% |   0.0000 |
| DEGRADED |   17 |   81.4 | 35.3% | 0.666 | 0.3 |       13 | 0.0% |   0.0% |    - | 60.0% |   0.2308 |
|      ALL |   31 |   55.9 | 32.3% | 0.660 | 0.3 |       27 | 0.0% |   0.0% |    - | 45.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 0.0% | 0.006 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   37.3 | 0.0% | 0.010 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   81.4 | 0.0% | 0.002 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   31 |   55.9 | 0.0% | 0.005 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    8 |   15.6 | 0.0% | 0.610 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    6 |   37.3 | 0.0% | 0.604 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |   81.4 | 0.0% | 0.502 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   55.9 | 0.0% | 0.550 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available