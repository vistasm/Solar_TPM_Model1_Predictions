# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-10-30 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 33.6% HIGHER than DEGRADED (8.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.6× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.6× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  121 |   99.9 | 30.6% | 0.642 | 0.4 |      121 | 8.1% |  15.0% | 0.5× | 33.7% |   0.1653 |
|      ALL |  217 |   65.0 | 35.0% | 0.678 | 0.5 |      217 | 19.7% |  32.6% | 0.9× | 35.7% |   0.2120 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  121 |   99.9 | 0.0% | 0.010 | 0.0 |      121 |    - |   0.0% |    - | 0.0% |   0.0579 |
|      ALL |  217 |   65.0 | 0.9% | 0.018 | 0.0 |      217 | 50.0% |   5.9% | 6.4× | 0.5% |   0.0783 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  121 |   99.9 | 0.0% | 0.516 | 0.0 |      121 |    - |   0.0% |    - | 0.0% |   0.0083 |
|      ALL |  217 |   65.0 | 0.5% | 0.553 | 0.0 |      217 | 0.0% |   0.0% |    - | 0.5% |   0.0230 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   13 |  108.0 | 53.8% | 0.656 | 0.8 |       13 | 14.3% |  33.3% | 0.6× | 60.0% |   0.2308 |
|      ALL |   13 |  108.0 | 53.8% | 0.656 | 0.8 |       13 | 14.3% |  33.3% | 0.6× | 60.0% |   0.2308 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   13 |  108.0 | 0.0% | 0.012 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|      ALL |   13 |  108.0 | 0.0% | 0.012 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   13 |  108.0 | 0.0% | 0.574 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   13 |  108.0 | 0.0% | 0.574 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available