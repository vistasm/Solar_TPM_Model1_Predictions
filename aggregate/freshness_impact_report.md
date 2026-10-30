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

🟢 **M+**: FRESH precision (41.7%) is 31.7% HIGHER than DEGRADED (10.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.8× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.9× the overall rate (0.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  135 |   99.6 | 29.6% | 0.642 | 0.3 |      135 | 10.0% |  18.2% | 0.6× | 31.9% |   0.1630 |
|      ALL |  231 |   66.9 | 34.2% | 0.676 | 0.5 |      231 | 20.2% |  33.3% | 1.0× | 34.4% |   0.2078 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  135 |   99.6 | 0.0% | 0.014 | 0.0 |      135 |    - |   0.0% |    - | 0.0% |   0.0519 |
|      ALL |  231 |   66.9 | 0.9% | 0.020 | 0.0 |      231 | 50.0% |   5.9% | 6.8× | 0.5% |   0.0736 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  135 |   99.6 | 0.0% | 0.521 | 0.0 |      135 |    - |   0.0% |    - | 0.0% |   0.0074 |
|      ALL |  231 |   66.9 | 0.4% | 0.554 | 0.0 |      231 | 0.0% |   0.0% |    - | 0.4% |   0.0216 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   27 |  101.9 | 37.0% | 0.650 | 0.5 |       27 | 20.0% |  40.0% | 1.1× | 36.4% |   0.1852 |
|      ALL |   27 |  101.9 | 37.0% | 0.650 | 0.5 |       27 | 20.0% |  40.0% | 1.1× | 36.4% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   27 |  101.9 | 0.0% | 0.031 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   27 |  101.9 | 0.0% | 0.031 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |   27 |  101.9 | 0.0% | 0.570 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   27 |  101.9 | 0.0% | 0.570 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available