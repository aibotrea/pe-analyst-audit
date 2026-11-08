# Track A Decision — COF.AX

**Decision ID**: `A_memo_triggered_a_COF_AX_20261108_233002_83fd9191`
**Flow context**: memo_triggered_a
**Decided at**: 2026-11-08T23:30:02.484595+00:00
**Decided by**: gp
**Source memo**: [`COF.AX_2026-11-08_equity_reit_v1@1.0_6451dbfd9ef1`](../memos/COF.AX_2026-11-08_equity_reit_v1@1.0_6451dbfd9ef1.md)
**GP cycle**: `A_cycle_2026-11-08T23:30:02.484595+00:00_74c6ae81`

## Action

- **Action**: `accept_with_downgrade`
- Conviction-implied target: 5.00%
- Executed size: 3.00%

## Reasoning

**Reason class**: `downgrade_judgement`

The memo has a 9% base-case E(R), about 75% PGain and an 11% yield, and it adds Office exposure. Office is only 0.98% of the portfolio, so this is the most underrepresented sector and the diversification benefit is real. I am not sizing at the full 5% conviction-implied target for three reasons. First, the asset_quality_concentration gate failed with a -1 override. Second, the filing bodies were mismatched, so gearing, coverage, WALE and NTA are unverified and the yield rests on secondary news. Third, office structural headwinds with about 91% occupancy and a bear case of -12% argue for a smaller position. A 3% position keeps meaningful exposure while limiting the cost of data and structural risk.

## Post-Decision Exposures

- Total invested: 96.47%
- Country: `{"Australia": 33.98, "Singapore": 33.1, "HongKong": 8.68, "Japan": 20.7}`
- Sector: `{"Diversified": 26.77, "Healthcare": 3.49, "Data Centre": 3.05, "Industrial/Logistics": 23.64, "Retail": 19.37, "Residential": 10.25, "Hospitality": 5.92, "Office": 3.98}`
