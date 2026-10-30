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

🟢 **M+**: FRESH precision (41.7%) is 33.8% HIGHER than DEGRADED (7.9%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.7× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.6× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  123 |   99.9 | 30.9% | 0.645 | 0.4 |      123 | 7.9% |  15.0% | 0.5× | 34.0% |   0.1626 |
|      ALL |  219 |   65.3 | 35.2% | 0.679 | 0.5 |      219 | 19.5% |  32.6% | 0.9× | 35.8% |   0.2100 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  123 |   99.9 | 0.0% | 0.011 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0569 |
|      ALL |  219 |   65.3 | 0.9% | 0.019 | 0.0 |      219 | 50.0% |   5.9% | 6.4× | 0.5% |   0.0776 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  123 |   99.9 | 0.0% | 0.517 | 0.0 |      123 |    - |   0.0% |    - | 0.0% |   0.0081 |
|      ALL |  219 |   65.3 | 0.5% | 0.554 | 0.0 |      219 | 0.0% |   0.0% |    - | 0.5% |   0.0228 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   15 |  106.4 | 53.3% | 0.678 | 0.7 |       15 | 12.5% |  33.3% | 0.6× | 58.3% |   0.2000 |
|      ALL |   15 |  106.4 | 53.3% | 0.678 | 0.7 |       15 | 12.5% |  33.3% | 0.6× | 58.3% |   0.2000 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   15 |  106.4 | 0.0% | 0.015 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |
|      ALL |   15 |  106.4 | 0.0% | 0.015 | 0.0 |       15 |    - |   0.0% |    - | 0.0% |   0.1333 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   15 |  106.4 | 0.0% | 0.577 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   15 |  106.4 | 0.0% | 0.577 | 0.0 |       15 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available