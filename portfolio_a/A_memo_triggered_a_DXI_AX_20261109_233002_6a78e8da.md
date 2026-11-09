# Track A Decision — DXI.AX

**Decision ID**: `A_memo_triggered_a_DXI_AX_20261109_233002_6a78e8da`
**Flow context**: memo_triggered_a
**Decided at**: 2026-11-09T23:30:02.663542+00:00
**Decided by**: gp
**Source memo**: [`DXI.AX_2026-11-09_equity_reit_v1@1.0_400500874385`](../memos/DXI.AX_2026-11-09_equity_reit_v1@1.0_400500874385.md)
**GP cycle**: `A_cycle_2026-11-09T23:30:02.663542+00:00_30ab36f4`

## Action

- **Action**: `reject`
- Conviction-implied target: 5.00%

## Reasoning

**Reason class**: `reject_capacity`

DXI.AX is a new name with a roughly 6.4% forward yield, a positive carry spread, an active buy-back and a diversified tenant base, so the thesis has merit. However, Industrial/Logistics is already 23.81% of the portfolio (GMG, A17U, O5RU, SKG, M44U, among others) and Australia is 34.24%, which raises the bar for this memo. DPS, gearing and AFFO coverage were not verified from filings, and the distribution_coverage gate carries a -1 override. Alpha is inflated by a negative benchmark return. I am sizing at 3% instead of the 5% conviction-implied target to reflect the sector and country overlap and the data gaps. [Plan netting: accept at 3.0% was reversed by a same-cycle cap-resolution dispose of the same ticker; capacity-rejected rather than executed and unwound.]

## Post-Decision Exposures

- Total invested: 93.59%
- Country: `{"Australia": 34.24, "Singapore": 31.04, "HongKong": 8.64, "Japan": 19.67}`
- Sector: `{"Diversified": 24.75, "Healthcare": 3.48, "Data Centre": 3.04, "Industrial/Logistics": 23.81, "Retail": 19.36, "Residential": 9.21, "Hospitality": 5.94, "Office": 3.99}`
