# Track A Decision — SKG.AX

**Decision ID**: `A_memo_triggered_a_SKG_AX_20260915_233001_8d3f753b`
**Flow context**: memo_triggered_a
**Decided at**: 2026-09-15T23:30:01.804368+00:00
**Decided by**: gp
**Source memo**: [`SKG.AX_2026-09-15_equity_reit_v1@1.0_7b5a133d0d30`](../memos/SKG.AX_2026-09-15_equity_reit_v1@1.0_7b5a133d0d30.md)
**GP cycle**: `A_cycle_2026-09-15T23:30:01.804368+00:00_ba0ece7e`

## Action

- **Action**: `accept_with_downgrade`
- Conviction-implied target: 5.00%
- Executed size: 3.00%

## Reasoning

**Reason class**: `downgrade_judgement`

SKG.AX presents a credible moderate-conviction thesis anchored by management internalisation, a 6% estimated yield, and a 68% PGain from the OU simulation. However, several merit-based factors warrant sizing below the conviction-3 implied 5% target. First, the portfolio is already heavily weighted toward Australia (27.53% country exposure) and the Diversified/Industrial/Retail complex; adding another Australian REIT at full size increases concentration risk in a market already well-represented. Second, the sector classification is 'Self-Storage' — not a represented sector in the current portfolio, which is a positive differentiator — but the ticker_dimensions map assigns it to Industrial/Logistics, where the portfolio already carries 21.56% sector exposure (A17U.SI at 7.99%, ME8U.SI at 2.98%, 3283.T at 3.05%, 3487.T at 3.07%, CIP.AX at 1.50%), making the bar for incremental Industrial/Logistics exposure high. Third, the FY26 DPU quantum could not be verified due to ASX pipeline body-capture gaps — a material data quality gap that introduces unquantified downside risk to the distribution yield assumption (Category B). Fourth, the post-FY26 results price decline of ~19% has been persistent and sustained over three months, signalling possible fundamental deterioration rather than mere sentiment overshoot. The bear case (-8%) is plausible and the invalidation conditions are non-trivial. Sizing at 3% (conviction-2 equivalent) appropriately reflects the genuine diversification benefit of a new self-storage sub-sector exposure while respecting the data limitations and existing Australian and logistics-adjacent concentration.

## Post-Decision Exposures

- Total invested: 94.16%
- Country: `{"Singapore": 30.64, "Japan": 32.99, "Australia": 30.53}`
- Sector: `{"Healthcare": 5.41, "Diversified": 29.96, "Retail": 11.13, "Office": 15.58, "Industrial/Logistics": 24.56, "Data Centre": 6.53, "Residential": 1.0}`
