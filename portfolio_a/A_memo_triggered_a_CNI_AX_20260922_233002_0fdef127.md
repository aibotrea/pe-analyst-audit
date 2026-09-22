# Track A Decision — CNI.AX

**Decision ID**: `A_memo_triggered_a_CNI_AX_20260922_233002_0fdef127`
**Flow context**: memo_triggered_a
**Decided at**: 2026-09-22T23:30:02.275635+00:00
**Decided by**: gp
**Source memo**: [`CNI.AX_2026-09-22_equity_reit_v1@1.0_f9b1428610de`](../memos/CNI.AX_2026-09-22_equity_reit_v1@1.0_f9b1428610de.md)
**GP cycle**: `A_cycle_2026-09-22T23:30:02.275635+00:00_071823d9`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_thesis_disagreement`

CNI.AX is a fund management company (Centuria Capital Group), not a REIT. The portfolio mandate is REIT-focused (all existing holdings are equity REITs across Australia, Japan, Singapore, and Hong Kong), and CNI.AX is explicitly described in the memo as a 'diversified Australian property funds manager' — a capital-light fee-income business with indirect property exposure. The memo acknowledges applying an equity_reit_v1 framework to a non-REIT entity, which introduces structural misfit: REIT-specific metrics (DPU coverage, gearing vs MAS/ASIC limits, WALE, occupancy) are proxied at the managed-fund level rather than directly observed at the CNI corporate level. Beyond mandate fit, the investment case is weak on its merits: historical volatility of 35.7% annualised is the highest of any memo in this batch, PGain of only 63.8% is the lowest, the bear scenario shows -18% expected return, the FY26 results triggered an ~11% single-day sell-off with volume anomaly that the memo cannot explain from filed data, distribution coverage carries a -1 gate override, and conviction is Low (score 2). The 43% derating from June 2026 peak is not a sufficient value catalyst when the underlying earnings quality is unverified. The portfolio already holds COF.AX (Office, Australia, 2.96%) which is itself one of CNI's managed REITs — owning the manager of a REIT we already hold creates layered, correlated exposure. Reject on thesis disagreement: wrong instrument type for mandate, weak risk/return profile relative to available alternatives.

## Post-Decision Exposures

- Total invested: 84.71%
- Country: `{"Singapore": 17.66, "Japan": 30.53, "Australia": 33.51, "HongKong": 3.0}`
- Sector: `{"Healthcare": 3.01, "Diversified": 27.42, "Retail": 14.5, "Office": 15.51, "Industrial/Logistics": 18.59, "Data Centre": 4.66, "Residential": 1.02}`
