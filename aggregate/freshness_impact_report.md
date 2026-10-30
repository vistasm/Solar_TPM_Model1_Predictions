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

🟢 **M+**: FRESH precision (41.7%) is 35.2% HIGHER than DEGRADED (6.5%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.5× the overall rate (0.9%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.6× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  115 |  100.1 | 27.0% | 0.628 | 0.3 |      115 | 6.5% |  10.5% | 0.4× | 30.2% |   0.1652 |
|      ALL |  211 |   64.1 | 33.2% | 0.671 | 0.5 |      211 | 20.0% |  31.1% | 0.9× | 33.7% |   0.2133 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  115 |  100.1 | 0.0% | 0.009 | 0.0 |      115 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |  211 |   64.1 | 0.9% | 0.018 | 0.0 |      211 | 50.0% |   6.7% | 7.0× | 0.5% |   0.0711 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  115 |  100.1 | 0.0% | 0.509 | 0.0 |      115 |    - |   0.0% |    - | 0.0% |   0.0087 |
|      ALL |  211 |   64.1 | 0.5% | 0.550 | 0.0 |      211 | 0.0% |   0.0% |    - | 0.5% |   0.0237 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    7 |  118.2 | 14.3% | 0.427 | 0.1 |        7 | 0.0% |   0.0% |    - | 20.0% |   0.2857 |
|      ALL |    7 |  118.2 | 14.3% | 0.427 | 0.1 |        7 | 0.0% |   0.0% |    - | 20.0% |   0.2857 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    7 |  118.2 | 0.0% | 0.000 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    7 |  118.2 | 0.0% | 0.000 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
| DEGRADED |    7 |  118.2 | 0.0% | 0.505 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |    7 |  118.2 | 0.0% | 0.505 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available