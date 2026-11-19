# Specialist Memo — DXI.AX

**Memo ID**: `DXI.AX_2026-11-19_equity_reit_v1@1.0_2fddbc2a946b`
**Ticker**: DXI.AX (Dexus Industria REIT)
**Market**: Australia
**Sector**: Industrial/Office (diversified Australian real estate)
**As of**: 2026-11-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
DXI offers a 6.7% distribution yield on a steady 16.6 cent distribution, about 2.5 percentage points above the 4.16% T-bill rate, with a sponsor-backed (Dexus) Australian real estate portfolio. The 12-month OU Monte Carlo gives an expected return of about 8.1% with 11.2% standard deviation, a PGain of 76.6% and CAPM alpha of 8.0%. Beta of 0.47 against IASP.L is low, but it carries currency-basis noise and the negative 5-year benchmark return inflates alpha. The numeric chain supports a score of 4. I cut it one step to 3 because gearing, AFFO coverage, occupancy and NTA could not be verified from issuer filings, and the stored filing bodies were mismatched. The ongoing buy-back is a small positive for per-security metrics.

## Quantitative Chain

- E(R): 0.0820
- Std dev: 0.1120
- P-gain: 0.7664
- CAPM alpha: 0.0804
- Beta: 0.4734
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0700
  - Higher-for-longer AUD rates or a stagflation-type shock lift cap rates by 50bps and cut valuations about 8%. Distribution is cut about 3% on higher interest costs and softer office occupancy. The P/NTA discount widens and gearing moves toward the top of the 30-40% range.
- **base**: E(R)=0.0820
  - Central case as built in the chain: 6.7% distribution yield, about 1.5% distribution growth, flat multiple and stable cap rates. The distribution is maintained near 16.6 cents and the buy-back gives mild support.
- **bull**: E(R)=0.1900
  - RBA easing and tighter cap rates narrow the P/NTA discount, adding about 8% of re-rating. Distribution growth reaches about 4% on industrial rent reversion and the buy-back is accretive. Total return is about 6.7% yield plus 4% growth plus 8% multiple expansion.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 2.48 (Cat A) — DXI.AX closing price of AUD 2.48 on 2026-11-19 from get_price.
- `distribution_yield` = 0.0669 (Cat A) — Reported FY26 distribution of 16.6 cents per security (from Kalkine news coverage, 'steady 16.6 cent distribution') divided by the AUD 2.48 price. The primary issuer filing was not retrieved.
- `distribution_growth_12m` = 0.015 (Cat C) — Assumed 1.5% distribution/FFO growth from fixed rent escalators and modest leasing, partly offset by higher funding costs. I could not verify FY27 guidance, so this is a model assumption. Scenarios test it from -3% to +4%.
- `multiple_change` = 0.0 (Cat C) — Assumes no change in the price/NTA or yield multiple over 12 months. The ongoing on-market buy-back is a mild support, but NTA and discount data were not verified, so I assumed no re-rating.
- `expected_return_build` = 0.082 (Cat B) — E(R) = 6.69% yield + 1.5% growth + 0.0% multiple change, rounded to 8.2%. The derivation is additive and the growth and multiple inputs are Category C.
- `risk_free_rate` = 0.0416 (Cat A) — US 3-month T-bill (DTB3) of 4.16% on 2026-11-18 from get_tbill_rate. It is a USD rate used as a proxy for the AUD risk-free rate, so there is a small currency mismatch.
- `expected_market_return` = -0.042932 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260 trading days). The benchmark is GBP-denominated and the figure includes FX effects. The negative Rm makes CAPM required return near zero, which flatters alpha.
- `filing_data_gap` = disclosed (Cat B) — get_stored_filings for DXI.AX returned bodies that belong to unrelated issuers (Elevra, Olympio, L1 Long Short, ResMed and others) under DXI headlines. I discarded them as off-topic. Gearing, AFFO coverage, occupancy, WALE and NTA could not be verified from issuer filings. ASX body capture is also parked.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Unverified fundamentals: gearing (AU convention below 40%), AFFO coverage, occupancy, WALE and NTA were not confirmed because the stored DXI filings were mismatched. A weaker reading on any of them would invalidate the conviction level.
- Higher-for-longer rates, or a stagflation pathway, would raise AUD debt costs and cap rates, compress valuations and pressure distribution cover.
- Currency-basis noise: beta and the benchmark return are measured against GBP-denominated IASP.L. The negative 5-year Rm (-4.3%) makes CAPM required return near zero and overstates alpha.
- Office exposure and asset-sale or recycling execution risk, including sponsor-driven strategic actions that could dilute unitholder value.
- E(R) growth and multiple inputs are Category C assumptions. Macro series other than DTB3 were not used, and this is a directional analysis, not a formal backtest.

## Invalidation Condition
Exit if reported gearing rises above 40% or the interest cover covenant tightens materially, if distribution coverage by AFFO falls below 1.0x for two consecutive half-year reporting periods, if the distribution is cut below roughly 16 cents per security, or if portfolio occupancy drops by more than 3 percentage points. Also exit if the Dexus sponsor relationship or management fee alignment deteriorates, or if a large NAV-destructive asset sale or equity raise is announced at a deep discount to NTA.
