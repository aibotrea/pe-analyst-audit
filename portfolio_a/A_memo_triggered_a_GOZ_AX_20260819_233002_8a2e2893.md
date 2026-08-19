# Track A Decision — GOZ.AX

**Decision ID**: `A_memo_triggered_a_GOZ_AX_20260819_233002_8a2e2893`
**Flow context**: memo_triggered_a
**Decided at**: 2026-08-19T23:30:02.282307+00:00
**Decided by**: gp
**Source memo**: [`GOZ.AX_2026-08-19_equity_reit_v1@1.0_37baf059a0b8`](../memos/GOZ.AX_2026-08-19_equity_reit_v1@1.0_37baf059a0b8.md)
**GP cycle**: `A_cycle_2026-08-19T23:30:02.282307+00:00_e7db1846`

## Action

- **Action**: `reject`
- Conviction-implied target: 5.00%

## Reasoning

**Reason class**: `reject_capacity`

GOZ.AX is already held at 1.95% weight (position_id 96) with a -6.06% local loss over 18 days, suggesting near-term price weakness. The memo sector is Office (Australian), which adds to an already elevated total Office exposure of ~13.92% portfolio-wide. The memo was conviction-downgraded internally from 4 to 3 due to the leverage gate fail (gearing ~41% exceeds the AU 40% convention ceiling), and the memo's own quant chain confirms this. The 8.2% yield is attractive and the PGain of 71.7% is supportive, but structural Australian CBD office headwinds, reliance on news-sourced (not primary ASX filing) figures for DPU and gearing, and the existing position's unrealised loss argue against adding at full conviction-3 size (5%). A token 1% top-up acknowledges the income attraction while respecting the sector crowding concern and the quality limitations of the data sourcing. [Plan netting: accept at 1.0% was reversed by a same-cycle cap-resolution dispose of the same ticker; capacity-rejected rather than executed and unwound.]

## Post-Decision Exposures

- Total invested: 94.69%
- Country: `{"Singapore": 30.11, "Japan": 34.13, "Australia": 30.45}`
- Sector: `{"Healthcare": 4.98, "Office": 13.92, "Diversified": 24.08, "Retail": 16.98, "Industrial/Logistics": 22.86, "Residential": 4.25, "Data Centre": 7.64}`
