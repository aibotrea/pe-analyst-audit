# Track A Decision — DCRU.SI

**Decision ID**: `A_memo_triggered_a_DCRU_SI_20261028_233002_aa22ad76`
**Flow context**: memo_triggered_a
**Decided at**: 2026-10-28T23:30:02.188569+00:00
**Decided by**: gp
**Source memo**: [`DCRU.SI_2026-10-28_equity_reit_v1@1.0_3cdccfaf01be`](../memos/DCRU.SI_2026-10-28_equity_reit_v1@1.0_3cdccfaf01be.md)
**GP cycle**: `A_cycle_2026-10-28T23:30:02.188569+00:00_802552b0`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_better_alternative`

Data Centre is a thin sector for us at 2.97% (AJBU.SI), so it is not heavily represented. The memo itself fails the asset_quality_concentration gate, with a small portfolio and tenant concentration. Its risk profile is poor: 25% volatility, a bear case of -18% against a base of 7.0%, and a beta correlation of 0.15 that makes the CAPM alpha unreliable. Leverage and coverage are unverified, and DPU growth is flat while refinancing costs rise. The base return matches K71U.SI but with roughly twice the volatility and a far worse downside. Given limited cash, I prefer K71U.SI.

## Post-Decision Exposures

- Total invested: 94.73%
- Country: `{"Singapore": 29.08, "Australia": 32.89, "Japan": 24.34, "HongKong": 8.42}`
- Sector: `{"Healthcare": 4.97, "Diversified": 25.13, "Industrial/Logistics": 26.31, "Data Centre": 2.97, "Office": 2.71, "Retail": 22.65, "Residential": 3.91, "Hospitality": 6.08}`
