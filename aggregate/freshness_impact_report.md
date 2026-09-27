# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (41.7%) is 35.0% HIGHER than DEGRADED (6.7%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (3.3%) is 3.3× the overall rate (1.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (1.7%) is 3.3× the overall rate (0.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 40.0% | 0.719 | 0.7 |       60 | 41.7% |  47.6% | 1.2× | 35.9% |   0.3500 |
|       OK |   36 |   33.0 | 41.7% | 0.729 | 0.6 |       36 | 13.3% |  40.0% | 1.0× | 41.9% |   0.1389 |
| DEGRADED |  103 |   96.8 | 29.1% | 0.644 | 0.3 |       99 | 6.7% |  11.8% | 0.4× | 34.2% |   0.1717 |
|      ALL |  199 |   60.2 | 34.7% | 0.682 | 0.5 |      195 | 20.3% |  32.6% | 0.9× | 36.2% |   0.2205 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 3.3% | 0.039 | 0.0 |       60 | 50.0% |  11.1% | 3.3× | 2.0% |   0.1500 |
|       OK |   36 |   33.0 | 0.0% | 0.013 | 0.0 |       36 |    - |   0.0% |    - | 0.0% |   0.0278 |
| DEGRADED |  103 |   96.8 | 0.0% | 0.011 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0505 |
|      ALL |  199 |   60.2 | 1.0% | 0.019 | 0.0 |      195 | 50.0% |   6.7% | 6.5× | 0.6% |   0.0769 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   60 |   13.6 | 1.7% | 0.626 | 0.0 |       60 | 0.0% |   0.0% |    - | 1.8% |   0.0667 |
|       OK |   36 |   33.0 | 0.0% | 0.557 | 0.0 |       36 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  103 |   96.8 | 0.0% | 0.508 | 0.0 |       99 |    - |   0.0% |    - | 0.0% |   0.0101 |
|      ALL |  199 |   60.2 | 0.5% | 0.553 | 0.0 |      195 | 0.0% |   0.0% |    - | 0.5% |   0.0256 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   15.2 | 16.7% | 0.532 | 0.2 |        6 | 0.0% |      - |    - | 16.7% |   0.0000 |
|       OK |    4 |   38.9 | 50.0% | 0.686 | 0.5 |        4 | 0.0% |      - |    - | 50.0% |   0.0000 |
| DEGRADED |   20 |  102.6 | 5.0% | 0.488 | 0.1 |       16 | 0.0% |   0.0% |    - | 7.1% |   0.1250 |
|      ALL |   30 |   76.7 | 13.3% | 0.523 | 0.1 |       26 | 0.0% |   0.0% |    - | 16.7% |   0.0769 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   15.2 | 0.0% | 0.000 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.002 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  102.6 | 0.0% | 0.000 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   76.7 | 0.0% | 0.000 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    6 |   15.2 | 0.0% | 0.541 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    4 |   38.9 | 0.0% | 0.557 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  102.6 | 0.0% | 0.524 | 0.0 |       16 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   30 |   76.7 | 0.0% | 0.532 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available