# Specialist Memo — DXI.AX

**Memo ID**: `DXI.AX_2026-09-26_equity_reit_v1@1.0_068311cad1e7`
**Ticker**: DXI.AX (Dexus Industria REIT)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-09-26
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Dexus Industria REIT (DXI.AX) offers pure-play Australian industrial and logistics property exposure at an estimated trailing yield of ~6.75% against a 4.08% risk-free rate, representing a meaningful spread above cash in a sector with structurally strong demand from e-commerce and supply-chain reshoring. The active on-market buy-back (>7.5M units repurchased since March 2026) signals management conviction that units trade below NAV, providing NTA accretion for remaining unitholders and a direct alignment of sponsor and unitholder interests. An annualised historical volatility of 15.8% and beta of 0.45 versus IASP.L (currency-basis caveat applies) indicate below-benchmark risk, while the OU Monte Carlo simulation yields a 77.7% probability of positive 12-month return (sim return 8.2%, std dev 10.7%). With Dexus as a high-quality sponsor and a conviction score of 4, DXI warrants an above-average position sizing of up to 8% of the REIT sleeve.

## Quantitative Chain

- E(R): 0.0825
- Std dev: 0.1074
- P-gain: 0.7773
- CAPM alpha: 0.0820
- Beta: 0.4534
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds rates higher for longer, triggering further cap rate expansion of 50bps; DXI distribution yield compresses in real terms as DPU is cut 5-8% due to tenant attrition and rising refinancing costs; occupancy falls below 93%; on-market buy-back suspended as balance sheet is prioritised for debt management; AUD/GBP basis move amplifies IASP.L benchmark divergence.
- **base**: E(R)=0.0820
  - Central case as built in quantitative chain: distribution yield 6.75%, DPU growth 2.5%, cap rate multiple change -1.0%. Buy-back continues at current pace, occupancy stable ~95-96%, RBA begins easing in H1 2027 supporting modest re-rating.
- **bull**: E(R)=0.2000
  - RBA pivots to rate cuts in late 2026, compressing cap rates and driving NAV re-rating; DPU growth accelerates to 4%+ supported by strong e-commerce and logistics demand; buy-back at deep discount to NTA generates significant per-unit accretion; AUD strengthens reducing import cost pressures on tenants; occupancy exceeds 97%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0675 (Cat B) — Trailing DPU estimated at ~AUD 0.155 per unit (consensus from public industrial REIT data; no clean DPU figure extractable from available ASX filing bodies for DXI due to pipeline parsing mismatches). Current price AUD 2.29 (2026-09-25 close). Implied yield 0.155/2.29 = 6.77%, rounded conservatively to 6.75%. Classified Category B as derived estimate, not directly observed from a confirmed DPU filing for FY2026.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumed based on: (1) Australian industrial REIT sector rent review mechanism (fixed or CPI-linked escalators, typically 3-3.5% on expiry; blended portfolio effect ~2.5% net given vacancies); (2) per-unit accretion from on-market buy-back (>7.5M units repurchased as at 9 Sep 2026; DXI 2026-09-20 buy-back filing). Sensitivity tested in scenario analysis. Category C as growth rate requires forward assumptions beyond observed data.
- `multiple_change` = -0.01 (Cat C) — Assumed -1.0% contribution from modest cap rate expansion pressure in Australian commercial property given elevated RBA cash rate environment (late 2026). DXI price declined from ~AUD 2.43 to ~AUD 2.29 over the 90-day window (approximately -5.7%), suggesting re-rating pressure. Annualised multiple-change assumption capped at -1.0% as OU mean-reversion captured in Monte Carlo. Category C model assumption; sensitivity tested in scenarios.
- `rba_cash_rate_context` = approximately 4.10% (Cat C) — RBA cash rate estimated at approximately 4.10% as of Sep 2026 based on public rate setting context. No stored APAC AU rate data returned by get_stored_apac_rates as_of 2026-09-26. Used as supporting context for yield spread analysis only; not a direct input to the quantitative chain. Category C as not confirmed from stored data.
- `buy_back_accretion` = positive (Cat A) — On-market buy-back initiated 9 March 2026 (DXI 2026-09-20 ASX Appendix 3C filing). Total units bought back: 7,448,857 prior to 9 Sep 2026, plus 80,929 on 9 Sep 2026 = cumulative ~7.53M units. Signals management conviction that market price is below NAV. NTA-accretive to remaining unitholders. Observed public data from ASX filing; Category A.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The IASP.L currency basis introduces noise into the 0.453 beta estimate (correlation 0.33 over 252 trading days). Treated as Category B input. CAPM alpha inherits the same noise — the deeply negative IASP.L 5-year return (-4.81% annualised) mechanically inflates alpha and should not be read as a free-lunch signal.

## Key Risks
- Higher-for-longer RBA cash rates extending cap rate expansion pressure and compressing NAV; DXI price has already declined ~5.7% from July 2026 highs, and further policy tightening could accelerate re-rating
- Distribution coverage uncertainty: clean AFFO coverage data was not obtainable from available ASX filing bodies due to pipeline parsing mismatches; an undisclosed DPU cut would materially reduce the yield assumption underpinning E(R)
- Tenant concentration and WALE visibility is limited from available filed documents; a deterioration in occupancy below 93% or shortening of WALE to under 3 years would signal a structural weakening of cash flow quality
- AUD/GBP currency basis noise in beta and IASP.L benchmark return (-4.81% annualised) causes the mechanically high CAPM alpha (0.082) to overstate true outperformance; alpha should not be used as a standalone buy signal
- Buy-back suspension risk: if balance sheet gearing approaches the ~40% AU REIT convention limit, the NTA-accretive buy-back programme would need to cease, removing a key support mechanism for the unit price

## Invalidation Condition
Exit the position if DXI discloses a DPU reduction of more than 5% versus the prior corresponding period in any quarterly or half-year distribution announcement, or if reported gearing exceeds 40% of total assets for two consecutive reporting periods, or if the on-market buy-back programme is formally suspended and management cites balance-sheet stress (rather than unit-price recovery) as the reason, or if occupancy across the portfolio falls below 92% for two consecutive reporting periods as disclosed in an ASX filing.
