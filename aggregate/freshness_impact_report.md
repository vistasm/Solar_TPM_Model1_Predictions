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

🟢 **M+**: FRESH precision (41.7%) is 34.0% HIGHER than DEGRADED (7.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.7× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.7× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  125 |   99.8 | 31.2% | 0.648 | 0.4 |      125 | 7.7% |  14.3% | 0.5× | 34.6% |   0.1680 |
|      ALL |  221 |   65.5 | 35.3% | 0.680 | 0.5 |      221 | 19.2% |  31.9% | 0.9× | 36.2% |   0.2127 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  125 |   99.8 | 0.0% | 0.014 | 0.0 |      125 |    - |   0.0% |    - | 0.0% |   0.0560 |
|      ALL |  221 |   65.5 | 0.9% | 0.021 | 0.0 |      221 | 50.0% |   5.9% | 6.5× | 0.5% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  125 |   99.8 | 0.0% | 0.519 | 0.0 |      125 |    - |   0.0% |    - | 0.0% |   0.0080 |
|      ALL |  221 |   65.5 | 0.4% | 0.554 | 0.0 |      221 | 0.0% |   0.0% |    - | 0.5% |   0.0226 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |  105.2 | 52.9% | 0.696 | 0.7 |       17 | 11.1% |  25.0% | 0.5× | 61.5% |   0.2353 |
|      ALL |   17 |  105.2 | 52.9% | 0.696 | 0.7 |       17 | 11.1% |  25.0% | 0.5× | 61.5% |   0.2353 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |  105.2 | 0.0% | 0.041 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |
|      ALL |   17 |  105.2 | 0.0% | 0.041 | 0.0 |       17 |    - |   0.0% |    - | 0.0% |   0.1176 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   17 |  105.2 | 0.0% | 0.580 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   17 |  105.2 | 0.0% | 0.580 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available