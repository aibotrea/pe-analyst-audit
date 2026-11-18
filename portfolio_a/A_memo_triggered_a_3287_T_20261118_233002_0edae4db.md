# Track A Decision — 3287.T

**Decision ID**: `A_memo_triggered_a_3287_T_20261118_233002_0edae4db`
**Flow context**: memo_triggered_a
**Decided at**: 2026-11-18T23:30:02.123819+00:00
**Decided by**: gp
**Source memo**: [`3287.T_2026-11-18_equity_reit_v1@1.0_f54a72c86ae9`](../memos/3287.T_2026-11-18_equity_reit_v1@1.0_f54a72c86ae9.md)
**GP cycle**: `A_cycle_2026-11-18T23:30:02.123819+00:00_dbf0c9e9`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_thesis_disagreement`

The asset_quality_concentration gate failed because rents depend on a single operator, Hoshino Resorts. The 4.7% yield is an unverified estimate, and leverage and coverage data are missing. E(R) of 6.2% is only about 200bp above the T-bill rate, which is thin compensation for tourism-cyclical variable rent. Japan is already 24.6% of the portfolio, and hospitality is already held at 4.55% through 8963.T and 8985.T. The bar for another hospitality name is higher, and this one does not clear it.

## Post-Decision Exposures

- Total invested: 94.75%
- Country: `{"Singapore": 27.71, "Australia": 33.74, "HongKong": 8.74, "Japan": 24.56}`
- Sector: `{"Healthcare": 2.5, "Diversified": 27.64, "Data Centre": 3.05, "Industrial/Logistics": 23.27, "Retail": 19.4, "Hospitality": 4.55, "Residential": 10.34, "Office": 4.01}`
