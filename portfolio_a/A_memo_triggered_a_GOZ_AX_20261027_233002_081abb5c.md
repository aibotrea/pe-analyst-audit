# Track A Decision — GOZ.AX

**Decision ID**: `A_memo_triggered_a_GOZ_AX_20261027_233002_081abb5c`
**Flow context**: memo_triggered_a
**Decided at**: 2026-10-27T23:30:02.252292+00:00
**Decided by**: gp
**Source memo**: [`GOZ.AX_2026-10-27_equity_reit_v1@1.0_89d8f4002f1b`](../memos/GOZ.AX_2026-10-27_equity_reit_v1@1.0_89d8f4002f1b.md)
**GP cycle**: `A_cycle_2026-10-27T23:30:02.252292+00:00_d410b5db`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_thesis_disagreement`

The memo's own leverage gate fails: gearing is about 41%, above the 40% Australian convention. Expected return is only 6.0%, which is about 2 points over the risk-free rate for an office-tilted REIT with negative DPU growth assumed. The yield, DPU guidance and gearing rest on recollection and secondary sources, because the stored filings were mismatched and no fundamentals were verified. The portfolio already has about 25% in Diversified and about 32% in Australia, with many Australian holdings, so the bar for another name is high. A thin 6% expected return with a failed gate and unverified data does not clear it.

## Post-Decision Exposures

- Total invested: 92.34%
- Country: `{"Singapore": 26.91, "Australia": 32.39, "Japan": 24.61, "HongKong": 8.44}`
- Sector: `{"Healthcare": 5.0, "Diversified": 25.14, "Industrial/Logistics": 23.77, "Data Centre": 2.98, "Office": 2.92, "Retail": 22.59, "Residential": 3.92, "Hospitality": 6.02}`
