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

🟢 **M+**: FRESH precision (41.7%) is 35.6% HIGHER than DEGRADED (6.1%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.5× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.6× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  117 |  100.1 | 28.2% | 0.631 | 0.3 |      117 | 6.1% |  10.5% | 0.4× | 31.6% |   0.1624 |
|      ALL |  213 |   64.4 | 33.8% | 0.673 | 0.5 |      213 | 19.4% |  31.1% | 0.9× | 34.5% |   0.2113 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  117 |  100.1 | 0.0% | 0.009 | 0.0 |      117 |    - |   0.0% |    - | 0.0% |   0.0513 |
|      ALL |  213 |   64.4 | 0.9% | 0.018 | 0.0 |      213 | 50.0% |   6.2% | 6.7× | 0.5% |   0.0751 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  117 |  100.1 | 0.0% | 0.510 | 0.0 |      117 |    - |   0.0% |    - | 0.0% |   0.0085 |
|      ALL |  213 |   64.4 | 0.5% | 0.551 | 0.0 |      213 | 0.0% |   0.0% |    - | 0.5% |   0.0235 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |  113.3 | 33.3% | 0.522 | 0.3 |        9 | 0.0% |   0.0% |    - | 42.9% |   0.2222 |
|      ALL |    9 |  113.3 | 33.3% | 0.522 | 0.3 |        9 | 0.0% |   0.0% |    - | 42.9% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |  113.3 | 0.0% | 0.000 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |    9 |  113.3 | 0.0% | 0.000 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    9 |  113.3 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    9 |  113.3 | 0.0% | 0.527 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available