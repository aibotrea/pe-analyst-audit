# Track A Decision — 8979.T

**Decision ID**: `A_memo_triggered_a_8979_T_20261004_233001_cd0fcae6`
**Flow context**: memo_triggered_a
**Decided at**: 2026-10-04T23:30:01.864277+00:00
**Decided by**: gp
**Source memo**: [`8979.T_2026-10-04_equity_reit_v1@1.0_cea8d074abb6`](../memos/8979.T_2026-10-04_equity_reit_v1@1.0_cea8d074abb6.md)
**GP cycle**: `A_cycle_2026-10-04T23:30:01.864277+00:00_b54d4825`

## Action

- **Action**: `accept_with_downgrade`
- Conviction-implied target: 3.00%
- Executed size: 1.00%

## Reasoning

**Reason class**: `downgrade_judgement`

8979.T is already held at ~0.98% weight. Conviction is Low (2), implying a target of 3%. Japan exposure is already 24.19% and the portfolio holds multiple diversified J-REITs (8953.T, 8961.T, 3292.T, 8976.T among others). The memo itself flags a governance concern — the July 2026 conflict-of-interest guideline change triggering a management_alignment gate override of -1 — and elevated LTV of ~53% with limited headroom. The E(R) of 5.9% is modest and the bear case (-8%) is meaningful. Given the heavy Japan exposure, the governance flag, and the low conviction rating, a modest top-up to 1% (maintaining roughly current weight) is appropriate rather than building to the 3% target. Further accumulation in Japan Diversified/Residential at this juncture is not merited on portfolio composition grounds.

## Post-Decision Exposures

- Total invested: 91.10%
- Country: `{"Singapore": 29.72, "Japan": 24.21, "Australia": 29.12, "HongKong": 8.05}`
- Sector: `{"Healthcare": 3.11, "Retail": 21.46, "Diversified": 24.78, "Office": 5.61, "Data Centre": 6.09, "Industrial/Logistics": 29.05, "Residential": 1.0}`
