# Track A Decision — 8986.T

**Decision ID**: `A_memo_triggered_a_8986_T_20261004_233001_eaaeef33`
**Flow context**: memo_triggered_a
**Decided at**: 2026-10-04T23:30:01.864277+00:00
**Decided by**: gp
**Source memo**: [`8986.T_2026-10-04_equity_reit_v1@1.0_7f489c56b779`](../memos/8986.T_2026-10-04_equity_reit_v1@1.0_7f489c56b779.md)
**GP cycle**: `A_cycle_2026-10-04T23:30:01.864277+00:00_b54d4825`

## Action

- **Action**: `accept_with_downgrade`
- Conviction-implied target: 3.00%
- Executed size: 1.00%

## Reasoning

**Reason class**: `downgrade_judgement`

8986.T (Daiwa Securities Living Investment Corporation) is a new position — not currently held. The memo carries conviction 2 (Low), target 3%. Japan residential is an underrepresented sub-sector (8979.T is the only current Residential-classified Japan holding at ~0.98%), which is a marginal positive. However, Japan total exposure is already 24.19%, distribution yield assumption is Category B (not confirmed from filed documents), DPU per unit not verified, distribution_coverage gate override of -1 applied, active refinancing of ¥43B bonds introduces near-term uncertainty, and E(R) of 5.2% is only modestly above the risk-free rate. The residential diversification benefit justifies a small new position, but the combination of low conviction, data gaps, and Japan concentration argues strongly against the full 3% target. 1% is appropriate as an exploratory position in an underrepresented sub-sector.

## Post-Decision Exposures

- Total invested: 92.08%
- Country: `{"Singapore": 29.72, "Japan": 25.19, "Australia": 29.12, "HongKong": 8.05}`
- Sector: `{"Healthcare": 3.11, "Retail": 21.46, "Diversified": 24.78, "Office": 5.61, "Data Centre": 6.09, "Industrial/Logistics": 29.05, "Residential": 1.98}`
