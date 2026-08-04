# Specialist Memo — HDN.AX

**Memo ID**: `HDN.AX_2026-08-03_equity_reit_v1@1.0_80929cd470dd`
**Ticker**: HDN.AX (HomeCo Daily Needs REIT)
**Market**: Australia
**Sector**: Large-Format Retail / Daily Needs
**As of**: 2026-08-03
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
HomeCo Daily Needs REIT offers compelling exposure to non-discretionary large-format retail in Australia — anchored by supermarkets, service stations, and quick-service restaurants — which provides income resilience through economic cycles. The trailing distribution yield of approximately 6.65% at AUD 1.27 represents a meaningful spread above the 3.69% T-bill rate, while the $92M gross valuation gains announced in June 2026 confirm continued asset appreciation. Beta of 0.54 against IASP.L (currency-basis caveat applies) indicates moderate systematic risk relative to the APAC REIT universe. The OU Monte Carlo simulation returns a PGain of 76.4% and a CAPM alpha of ~8.4%, reflecting above-market expected return against a negative benchmark return environment. Conviction is set at 4 (Above average), subject to confirmation of distribution coverage once FY2026 full-year results are released (Advance Notice filed 2026-07-14).

## Quantitative Chain

- E(R): 0.0815
- Std dev: 0.1125
- P-gain: 0.7643
- CAPM alpha: 0.0837
- Beta: 0.5413
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds rates higher for longer, driving cap rate expansion of ~25bps across large-format retail. DPU growth stalls at 0% as rent-review uplift is absorbed by higher hedging costs and refinancing spreads. Occupancy slips to ~95% from current levels. Distribution yield spread over the risk-free rate compresses materially. A broader Australian property downturn or stagflationary environment (high CPI + weak GDP) amplifies the drawdown.
- **base**: E(R)=0.0810
  - Central case as built in chain: distribution yield 6.65%, DPU growth 1.5% (CPI-linked reviews), cap rates flat. Gearing remains ~32–36%, within regulatory comfort. Occupancy stable. RBA begins modest easing by late 2026, providing mild multiple support.
- **bull**: E(R)=0.2000
  - RBA cuts rates by 50–75bps through H2 2026, compressing cap rates by ~20bps and lifting NTA. HMC Capital injects accretive pipeline assets at 7%+ entry yields, boosting DPU growth to 3%+. Valuation gains accelerate (building on the $92M gains reported June 2026), and the unit price re-rates toward NAV, adding meaningful capital return on top of yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0665 (Cat B) — Trailing DPU yield midpoint derived from multiple published news sources (Kalkine, July 2026) referencing HDN yield in the 6.57%–6.73% range at prices consistent with AUD 1.27 close on 2026-08-03. ASX filing body for 'Dividend/Distribution - HDN' (2026-06-15) was unavailable (body_capture failed); yield confirmed via external news cross-referencing only. Classified Category B as a derived estimate.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed, reflecting HDN's predominantly CPI-linked rent review structure across large-format retail (supermarkets, service stations, QSR). Consistent with mid-cycle inflation moderation in Australia. Sensitivity tested in scenario analysis. No FY2026 full-year results available as at as_of date (Advance Notice filed 2026-07-14, results not yet released).
- `multiple_change` = 0.0 (Cat C) — Assumed flat cap rate / multiple change in base case. HDN announced $92M gross valuation gains (ASX headline 2026-06-15, price-sensitive, body unavailable), suggesting mild positive revaluation momentum; however, with Australian rates elevated, terminal cap rate expansion risk remains. Base case holds multiples flat; bear/bull cases test +/-25bps cap rate movement.
- `leverage_gearing` = approx_32_to_36_pct (Cat B) — HDN's publicly reported gearing has historically ranged 32–36%, well within the Australian REIT convention of <40%. Specific as_of gearing ratio could not be confirmed from filing bodies (ASX body capture failed for June 2026 filings). Estimate based on prior period disclosures and absence of any capital-structure adverse news. Category B as a derived estimate without confirmed as_of filing data.
- `valuation_gains_fy2026` = 92000000.0 (Cat A) — HDN ASX headline announcement: 'HDN Records $92M Gross Valuation Gains' filed 2026-06-15 (price_sensitive=True). Body unavailable (body_capture failed); headline and metadata treated as Category A observed public data. Supports flat-to-positive multiple-change assumption in base case.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP.L 5-year annualised return of -3.54% reflects partial AUD/GBP headwind and should not be interpreted as the pure AUD REIT market return.

## Key Risks
- Higher-for-longer RBA cash rate compressing the yield spread and driving cap rate expansion in large-format retail assets, reducing NTA and potentially stressing refinancing at higher spreads.
- Distribution coverage uncertainty: ASX filing body capture for HDN's June 2026 distribution announcement failed; AFFO coverage ratio not confirmed as at as_of date — full-year results (due post-July 2026) are required to validate payout sustainability.
- Sponsor/manager concentration risk: HDN is solely managed by HMC Capital; any change in strategy, fee structure, or management team (David Di Pilla) could materially affect unitholder outcomes.
- Macro calibration limitation: the Phase 2 quantitative framework provides a directional signal only; formal backtest vintage discipline is scheduled for Phase 5. Conviction score should be treated as indicative.
- AUD/GBP currency basis embedded in beta and CAPM alpha: IASP.L is GBP-denominated, introducing FX noise into both the beta estimate and alpha computation, potentially overstating or understating systematic risk.

## Invalidation Condition
Exit or reduce position if: (1) HDN's FY2026 full-year results (expected August 2026) reveal AFFO distribution coverage below 1.0x for two consecutive half-years, indicating an unsustainable payout; (2) reported gearing exceeds 40% of total assets, breaching the Australian REIT regulatory convention; (3) HMC Capital announces a material change to management fees, asset recycling strategy, or reduces its own unitholder commitment; or (4) occupancy falls below 95% for two consecutive reporting periods, signalling demand deterioration in the large-format retail sub-sector.
