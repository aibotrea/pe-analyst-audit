# Track A Decision — SGP.AX

**Decision ID**: `A_memo_triggered_a_SGP_AX_20260915_100014_6ddea2c4`
**Flow context**: memo_triggered_a
**Decided at**: 2026-09-15T10:00:14.358222+00:00
**Decided by**: gp
**Source memo**: [`SGP.AX_2026-09-14_equity_reit_v1@1.0_55d1e53eb4ae`](../memos/SGP.AX_2026-09-14_equity_reit_v1@1.0_55d1e53eb4ae.md)
**GP cycle**: `A_cycle_2026-09-15T10:00:14.358222+00:00_55dc2937`

## Action

- **Action**: `accept_with_downgrade`
- Conviction-implied target: 8.00%
- Executed size: 5.00%

## Reasoning

**Reason class**: `downgrade_judgement`

SGP.AX conviction-4 implies 8.0%, but a downgrade to 5.0% is warranted on two non-cap grounds. First, portfolio composition: Australia is already the largest single-country exposure at 33.72%, and the Diversified sector at 27.89% is the most heavily represented sector in the book. SGP.AX is itself classified Diversified/Australia, and the portfolio already holds SGP.AX at ~2.93% across two legs — incremental addition compounds both concentrations simultaneously. Second, memo-specific quality concerns: the distribution yield (6.77%) and DPU estimate are Category B (FY2026 actuals not filed; reliant on a news headline price-spike inference), gearing is estimated Category B, and the CAPM alpha of 14.5% is explicitly flagged as anomalously inflated by the GBP/AUD benchmark basis — the memo itself instructs it should not be used as a precision signal. The OU PGain of 70.1% is the weakest of the three non-speculative candidates. The thesis is sound (RBA easing, residential recovery, top-end FFO), but the information quality and concentration overlay justify sizing at 5% rather than 8%.

## Post-Decision Exposures

- Total invested: 96.32%
- Country: `{"Singapore": 27.52, "Japan": 33.01, "Australia": 35.79}`
- Sector: `{"Healthcare": 5.4, "Diversified": 29.96, "Retail": 16.02, "Office": 15.58, "Industrial/Logistics": 19.42, "Data Centre": 8.93, "Residential": 1.0}`
