# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-10-23_equity_reit_v1@1.0_41fbb80fa684`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Diversified/Office
**As of**: 2026-10-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Dexus is a large Australian diversified property group with an office-heavy portfolio and a funds management platform. At AUD 5.75 it offers a distribution yield of about 6.9%, well above the 4.04% US T-bill rate. News suggests FY27 AFFO guidance steps lower while the FY26 distribution was held, and an active on-market buy-back is under way. The OU Monte Carlo gives a 12-month simulated return of about 4.9% with a standard deviation of about 14.4%, a PGain of 63%, and a CAPM alpha of 6.1% (which is inflated by the negative IASP.L market return). Beta of 0.59 versus IASP.L carries the currency-basis caveat. This supports moderate conviction with a mid-sized position.

## Quantitative Chain

- E(R): 0.0500
- Std dev: 0.1435
- P-gain: 0.6345
- CAPM alpha: 0.0611
- Beta: 0.5945
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or higher-for-longer rate pathway lifts Australian bond yields and widens office cap rates by 25-50bps. FY27 AFFO falls below guidance, distribution is cut about 10% as coverage drops under 1.0x, and the multiple de-rates. Office valuations are written down.
- **base**: E(R)=0.0500
  - Central case as built in the chain: yield of about 6.9%, distribution drift of -1.5% in line with softer FY27 AFFO guidance, and no multiple change. The buy-back gives mild support.
- **bull**: E(R)=0.1900
  - RBA easing and tighter cap rates drive a re-rating of 6-8%. Office leasing recovers and capital recycling or funds-management initiatives add to earnings. The distribution is held at 40c and the buy-back narrows the discount to NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `share_price` = 5.75 (Cat A) — DXS.AX closing price on 2026-10-23 from get_price, in AUD.
- `distribution_yield` = 0.069 (Cat B) — Assumes FY26 distribution of about 40.0c per security, held flat per 2026 news (Kalkine, 2026-10-01). I did not verify the exact DPS from a primary filing. 40.0c divided by AUD 5.75 gives about 6.9%.
- `dpu_growth_12m` = -0.015 (Cat C) — News reports FY27 AFFO guidance stepping lower while FY26 distribution was maintained. I assume a modest -1.5% distribution drift over 12 months. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No re-rating or de-rating assumed. Price has ranged AUD 5.4 to 6.1 over the last 90 days. The ongoing on-market buy-back is treated as supportive but not quantified.
- `expected_return_build` = 0.05 (Cat B) — E(R) is about 6.9% yield, minus 1.5% growth drift, plus 0% multiple change. This is about 5.4%, rounded down to 5.0% for conservatism and unverified inputs.
- `risk_free_rate` = 0.0404 (Cat A) — FRED DTB3 3-month T-bill, observed 2026-10-22. It is a USD rate used as the CAPM risk-free input per methodology.
- `expected_market_return` = -0.0463 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return (1260-day lookback). It is GBP-denominated and absorbs FX noise.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_body_gap` = disclosed (Cat B) — The stored DXS.AX 'buy-back' filings returned for as_of 2026-10-23 had bodies from unrelated issuers (mining, education, telco). I extracted no facts from them. Gearing, AFFO coverage, occupancy and WALE were not verified from primary filings.

## Key Risks
- Further office cap-rate expansion or valuation write-downs if Australian rates stay higher for longer, and a falling AFFO trajectory could squeeze distribution coverage.
- Several inputs are unverified: gearing, AFFO coverage, occupancy and the exact DPS. The stored filing bodies were mismatched and unusable, so the gate statuses marked info rest on incomplete data.
- Beta of 0.59 (correlation 0.33) against the GBP-denominated IASP.L is noisy. The negative 5-year benchmark return of -4.6% inflates CAPM alpha, so alpha is a weak supporting signal.
- Elevated realised volatility of about 21% and a sharp sell-off from about AUD 6.07 in August to about AUD 5.4 in late September show sensitivity to rate and sentiment shocks.
- The risk-free rate is a USD T-bill applied to an AUD asset, creating a currency mismatch in the CAPM inputs.

## Invalidation Condition
Exit if Dexus cuts its distribution below roughly 36c per security or reports AFFO payout coverage below 1.0x for two consecutive reporting periods. Also exit if look-through gearing rises above about 40%, or if office portfolio occupancy falls materially with further valuation write-downs of more than 5% in a single half. Any of these would show the earnings and balance-sheet support for the yield has failed.
