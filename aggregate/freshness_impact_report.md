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

🟢 **M+**: FRESH precision (41.7%) is 33.3% HIGHER than DEGRADED (8.3%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.6× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.6× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  120 |  100.0 | 30.0% | 0.640 | 0.4 |      120 | 8.3% |  15.0% | 0.5× | 33.0% |   0.1667 |
|      ALL |  216 |   64.8 | 34.7% | 0.677 | 0.5 |      216 | 20.0% |  32.6% | 0.9× | 35.3% |   0.2130 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  120 |  100.0 | 0.0% | 0.010 | 0.0 |      120 |    - |   0.0% |    - | 0.0% |   0.0583 |
|      ALL |  216 |   64.8 | 0.9% | 0.019 | 0.0 |      216 | 50.0% |   5.9% | 6.3× | 0.5% |   0.0787 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  120 |  100.0 | 0.0% | 0.515 | 0.0 |      120 |    - |   0.0% |    - | 0.0% |   0.0083 |
|      ALL |  216 |   64.8 | 0.5% | 0.553 | 0.0 |      216 | 0.0% |   0.0% |    - | 0.5% |   0.0231 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |  109.0 | 50.0% | 0.632 | 0.8 |       12 | 16.7% |  33.3% | 0.7× | 55.6% |   0.2500 |
|      ALL |   12 |  109.0 | 50.0% | 0.632 | 0.8 |       12 | 16.7% |  33.3% | 0.7× | 55.6% |   0.2500 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |  109.0 | 0.0% | 0.013 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   12 |  109.0 | 0.0% | 0.013 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   12 |  109.0 | 0.0% | 0.566 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   12 |  109.0 | 0.0% | 0.566 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available