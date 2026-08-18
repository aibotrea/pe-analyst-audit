# Track A Decision — CLW.AX

**Decision ID**: `A_memo_triggered_a_CLW_AX_20260818_233002_537ca964`
**Flow context**: memo_triggered_a
**Decided at**: 2026-08-18T23:30:02.118914+00:00
**Decided by**: gp
**Source memo**: [`CLW.AX_2026-08-18_equity_reit_v1@1.0_ae2fbbf72bb4`](../memos/CLW.AX_2026-08-18_equity_reit_v1@1.0_ae2fbbf72bb4.md)
**GP cycle**: `A_cycle_2026-08-18T23:30:02.118914+00:00_e5bf1dd0`

## Action

- **Action**: `accept_with_downgrade`
- Conviction-implied target: 5.00%
- Executed size: 1.50%
- Binding constraint: `total_invested_cap`

## Reasoning

**Reason class**: `downgrade_concentration`

CLW.AX is not currently held and brings Australian Diversified REIT exposure. The Diversified sector is already the portfolio's second-largest at 21.17% and Australia is at 27.98%, both meaningful levels; however, CLW.AX is a qualitatively distinct asset — long-WALE government and social-infrastructure tenant base, recently completed $2B refinancing, Charter Hall sponsor with strong pipeline — that adds defensive duration differentiation within the Diversified sector rather than duplicating existing holdings (SGP.AX, GOZ.AX, DXS.AX are shorter-WALE or different profile). Conviction 3 implies 5% target, and the memo supports this with a 76.3% PGain, 8.2% sim return, and sound qualitative gates (one leverage gate override applied at the memo level, appropriately reflected in conviction 3 rather than 4). The 6.8% trailing yield is attractive. One gate override for leverage (info, -1) is already baked into the conviction score. Accepting at the full conviction-3 implied 5% is appropriate given the additive diversification value and distinct lease profile, despite elevated Diversified and Australia sector weights. [Plan netting: target reduced from 5.0% to 1.5% — a same-cycle cap-resolution dispose targeted this ticker at the lower weight; netted to a single acquisition.]

## Post-Decision Exposures

- Total invested: 94.79%
- Country: `{"Singapore": 31.27, "Japan": 34.04, "Australia": 29.48}`
- Sector: `{"Healthcare": 4.97, "Office": 13.85, "Diversified": 22.67, "Retail": 17.11, "Industrial/Logistics": 22.08, "Residential": 4.32, "Data Centre": 9.8}`
