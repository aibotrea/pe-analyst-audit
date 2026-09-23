# Track A Decision — TS0U.SI

**Decision ID**: `A_memo_triggered_a_TS0U_SI_20260923_233002_132e4c44`
**Flow context**: memo_triggered_a
**Decided at**: 2026-09-23T23:30:02.848351+00:00
**Decided by**: gp
**Source memo**: [`TS0U.SI_2026-09-23_equity_reit_v1@1.0_58f5e2b60927`](../memos/TS0U.SI_2026-09-23_equity_reit_v1@1.0_58f5e2b60927.md)
**GP cycle**: `A_cycle_2026-09-23T23:30:02.848351+00:00_22c5d747`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_capacity`

TS0U.SI is already held at 0.99% of NAV (position_id 144). The memo conviction score is 2 (Low), implying a 3% target weight. Current Singapore Diversified exposure is elevated (TS0U.SI itself, P40U.SI, and others contribute to Singapore total of ~17.6%), and Diversified sector is the largest sector exposure at 27.3%. However, TS0U.SI is a distinct Singapore office/hospitality REIT with a 7.3% yield, 69.5% PGain, and a clear thesis differentiated from the other Singapore Diversified holdings. The incremental add from ~1% to 3% is modest and justified on per-memo merit. The management-alignment gate failure is already reflected in the conviction score of 2 and the -1 override. Accept at the conviction-implied 3% target; cap-driven trimming will be handled deterministically if needed. [Plan netting: accept at 3.0% was reversed by a same-cycle cap-resolution dispose of the same ticker; capacity-rejected rather than executed and unwound.]

## Post-Decision Exposures

- Total invested: 86.02%
- Country: `{"Singapore": 17.6, "Japan": 30.46, "Australia": 34.93, "HongKong": 3.03}`
- Sector: `{"Healthcare": 3.03, "Diversified": 27.3, "Retail": 14.46, "Office": 15.55, "Industrial/Logistics": 20.17, "Data Centre": 4.49, "Residential": 1.02}`
