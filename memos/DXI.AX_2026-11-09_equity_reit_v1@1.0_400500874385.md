# Specialist Memo — DXI.AX

**Memo ID**: `DXI.AX_2026-11-09_equity_reit_v1@1.0_400500874385`
**Ticker**: DXI.AX (Dexus Industria REIT)
**Market**: Australia
**Sector**: Industrial
**As of**: 2026-11-09
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
DXI offers Australian industrial REIT exposure with a forward yield of about 6.4%, which is roughly 2.4 points above the 4.01% T-bill. Recent headlines point to an FY26 FFO guidance beat, solid leasing spreads and an active on-market buy-back. The beta of 0.48 against IASP.L carries the currency-basis caveat. The OU Monte Carlo gives a 12-month mean of 8.3% and a PGain of 77%, which would support a score of 4. I cut conviction by one step to 3 because fundamentals (DPS, gearing, AFFO coverage, occupancy) could not be verified from filings, and because the CAPM alpha is inflated by a negative trailing benchmark return.

## Quantitative Chain

- E(R): 0.0840
- Std dev: 0.1130
- P-gain: 0.7700
- CAPM alpha: 0.0855
- Beta: 0.4821
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Stagflation or higher-for-longer pathway: RBA stays at or above 4.6% and AU bond yields rise. Industrial cap rates expand about 50bps, a 10% or larger valuation drop. Distribution growth stalls at 0% and AFFO coverage falls below 1.0x. Yield 6.4% with 0% growth and about -14% multiple change gives roughly -8%.
- **base**: E(R)=0.0840
  - Central case as built: 6.4% yield, 2% growth from rent reviews and leasing spreads, flat cap rates and P/NAV, buy-back continuing. OU Monte Carlo mean is 8.35% with a standard deviation of 11.3%.
- **bull**: E(R)=0.1900
  - Rate cuts compress cap rates by 25bps and the P/NAV discount narrows by 5 to 6 points. Distribution growth reaches 4% on stronger rent reviews and accretive development or buy-backs. Yield 6.4% + 4% growth + about 8.5% re-rating.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 2.47 (Cat A) — DXI.AX latest close 2026-11-09 (AUD) from get_price.
- `distribution_yield` = 0.064 (Cat B) — Estimated forward distribution yield of about 6.4% on the AUD 2.47 price. It is based on my recollection of recent DPS levels, not on a figure retrieved from an issuer filing. The stored filings returned for this ticker were unrelated documents (other issuers' notices), so FY26 DPS was not verified. Treated as Category B and flagged for verification.
- `dpu_growth` = 0.02 (Cat C) — Assumed 2% annual distribution/FFO growth from contracted rent escalators and positive leasing spreads. Press headlines (Kalkine/Morningstar, Aug-Nov 2026) report an FY26 FFO guidance beat and strong industrial leasing. Sensitivity: each 1pt change in growth moves E(R) by about 1pt, as shown in the bear and bull cases.
- `multiple_change` = 0.0 (Cat C) — Assumed flat cap rates and P/NAV over 12 months. The ongoing on-market buy-back (daily Appendix 3C notices through 2026-11-09) suggests management sees a discount to NAV, but no re-rating is assumed. Sensitivity: 25bps of cap-rate move is roughly 4-5% of NAV.
- `expected_return_build` = 0.084 (Cat C) — E(R) = 6.4% yield + 2.0% growth + 0.0% multiple change = 8.4%. Composite of Category B and C components.
- `risk_free_rate` = 0.0401 (Cat A) — FRED DTB3 3-month T-bill 4.01% observed 2026-11-06. The AU policy rate is 4.60% per BIS, observed 2026-10-29.
- `expected_market_return` = -0.04619 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260-day lookback). It is negative, so CAPM alpha is mechanically inflated.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_body_gap` = disclosed (Cat B) — ASX filing bodies were returned for the 8 most recent DXI.AX stored rows, but their text belonged to unrelated issuers. Only the headlines (daily buy-back notices) were usable. Gearing, AFFO coverage, occupancy, WALE and tenant data could not be sourced and are not asserted as facts.

## Key Risks
- Data gap: DPS, gearing, AFFO coverage, WALE and tenant concentration were not verified from issuer filings, because the stored filing bodies belonged to unrelated issuers. The yield and quality gates rest on unverified recollection and headlines.
- Rates: RBA policy at 4.6% and a 4.01% T-bill compress the yield spread. Further rate rises or higher bond yields would expand cap rates and cut NAV.
- Benchmark and currency noise: the correlation with IASP.L is only 0.34 and the benchmark is GBP-denominated. The negative 5-year benchmark return (-4.6%) mechanically inflates CAPM alpha, so alpha should be read cautiously.
- Sponsor and governance: DXI's relationship with Dexus (the manager and a major holder) and any change in strategic direction, such as a corporate action, could change the thesis. Industrial rent growth could also moderate as new supply arrives.
- Limitations: the OU Monte Carlo is mean-reverting and may understate tail risk. The macro series set is limited to DTB3 and the BIS AU policy rate.

## Invalidation Condition
Exit if the next DXI results or quarterly update show distribution coverage below 1.0x AFFO, a DPS cut, or gearing above about 40% (the Australian convention cap) with a need for equity raising at a discount. Also exit if portfolio occupancy falls below about 94% for two consecutive reporting periods, or if industrial valuations show cap-rate expansion above 50bps. Exit too if Dexus materially reduces its commitment to the vehicle, or if the 12-month total return thesis is invalidated by a price fall of more than 15% without a matching improvement in fundamentals.
