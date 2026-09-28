# Track A Decision — MGR.AX

**Decision ID**: `A_memo_triggered_a_MGR_AX_20260928_233001_f683c0ca`
**Flow context**: memo_triggered_a
**Decided at**: 2026-09-28T23:30:01.865663+00:00
**Decided by**: gp
**Source memo**: [`MGR.AX_2026-09-28_equity_reit_v1@1.0_fa3cc5255098`](../memos/MGR.AX_2026-09-28_equity_reit_v1@1.0_fa3cc5255098.md)
**GP cycle**: `A_cycle_2026-09-28T23:30:01.865663+00:00_c58e335d`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_capacity`

MGR.AX conviction score is 2 (Low), implying a 3% target weight. The portfolio already holds MGR.AX at ~0.97% weight, so this is effectively a top-up. Conviction is appropriately low given the hybrid developer/REIT structure, unconfirmed DPS (Category B), and a -1 distribution coverage gate override reflecting AFFO uncertainty. The Diversified sector is already heavily represented in the portfolio (~23.1%), and Australia exposure is at ~34.9%, both elevated, which ordinarily raises the bar. However, MGR.AX's stapled structure with BTR and residential exposure provides genuine differentiation within the Diversified bucket, and the 3% conviction-implied cap is already conservative. The PGain of 67.5% and base-case return of 7.0% are modest but acceptable at this size. Accept at conviction-implied 3% (which subsumes the existing ~0.97% holding — deterministic resolver will handle sizing against existing position). [Plan netting: accept at 3.0% was reversed by a same-cycle cap-resolution dispose of the same ticker; capacity-rejected rather than executed and unwound.]

## Post-Decision Exposures

- Total invested: 91.45%
- Country: `{"Singapore": 16.54, "Japan": 32.9, "Australia": 34.94, "HongKong": 7.07}`
- Sector: `{"Healthcare": 3.06, "Retail": 19.48, "Diversified": 23.11, "Office": 13.77, "Industrial/Logistics": 26.57, "Data Centre": 4.44, "Residential": 1.01}`
