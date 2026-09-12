# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.4%) is 3.1× the overall rate (1.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.1× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 40.7% | 0.726 | 0.8 |       57 | 41.7% |  47.6% | 1.1× | 38.9% |   0.3684 |
|       OK |   35 |   32.9 | 40.0% | 0.722 | 0.6 |       34 | 14.3% |  40.0% | 1.0× | 41.4% |   0.1471 |
| DEGRADED |   91 |   90.3 | 33.0% | 0.675 | 0.4 |       90 | 6.7% |  11.8% | 0.3× | 38.4% |   0.1889 |
|      ALL |  185 |   55.0 | 36.8% | 0.700 | 0.5 |      181 | 20.6% |  32.6% | 0.9× | 39.1% |   0.2376 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 3.4% | 0.039 | 0.0 |       57 | 50.0% |  11.1% | 3.2× | 2.1% |   0.1579 |
|       OK |   35 |   32.9 | 0.0% | 0.013 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
| DEGRADED |   91 |   90.3 | 0.0% | 0.012 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |  185 |   55.0 | 1.1% | 0.021 | 0.0 |      181 | 50.0% |   6.7% | 6.0× | 0.6% |   0.0829 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   59 |   13.7 | 1.7% | 0.629 | 0.0 |       57 | 0.0% |   0.0% |    - | 1.9% |   0.0702 |
|       OK |   35 |   32.9 | 0.0% | 0.557 | 0.0 |       34 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   91 |   90.3 | 0.0% | 0.507 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0111 |
|      ALL |  185 |   55.0 | 0.5% | 0.555 | 0.0 |      181 | 0.0% |   0.0% |    - | 0.6% |   0.0276 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 50.0% | 0.721 | 0.6 |        8 | 40.0% | 100.0% | 1.6× | 50.0% |   0.2500 |
|       OK |    5 |   36.0 | 20.0% | 0.617 | 0.2 |        4 | 0.0% |      - |    - | 25.0% |   0.0000 |
| DEGRADED |   15 |   41.7 | 33.3% | 0.695 | 0.5 |       14 | 40.0% |  40.0% | 1.1× | 33.3% |   0.3571 |
|      ALL |   30 |   31.5 | 36.7% | 0.691 | 0.5 |       26 | 36.4% |  57.1% | 1.4× | 36.8% |   0.2692 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 0.0% | 0.002 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    5 |   36.0 | 0.0% | 0.012 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   41.7 | 0.0% | 0.013 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   30 |   31.5 | 0.0% | 0.009 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   13.9 | 0.0% | 0.587 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    5 |   36.0 | 0.0% | 0.565 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   15 |   41.7 | 0.0% | 0.554 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   31.5 | 0.0% | 0.567 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available