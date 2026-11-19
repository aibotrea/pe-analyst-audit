# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-11-19_equity_reit_v1@1.0_84dba63b9c7e`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics (incl. data centre development)
**As of**: 2026-11-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is a global industrial and logistics developer-manager with a growing data centre pipeline. It has low distribution yield (about 1%) so returns depend on earnings growth and the sustaining of its premium multiple. The 12-month OU Monte Carlo gives a simulated return of about 7.9% with 20.7% standard deviation, which implies a PGain of 64.9%. That supports Moderate conviction (3/5). Beta of 0.78 versus IASP.L is low quality, with 0.30 correlation and a currency-basis caveat. The alpha of 10.4% is flattered by a negative trailing benchmark return, so conviction rests mainly on PGain. The new 9.9% NEXTDC stake adds data centre exposure but also concentration and capital allocation risk.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.2068
- P-gain: 0.6489
- CAPM alpha: 0.1040
- Beta: 0.7768
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2200
  - Premium multiple compresses sharply because of an AI/data-centre capex sentiment reversal or higher-for-longer rates (a stagflation-style pathway). Development margins and WIP completions slip, and growth falls to about 2%. The NEXTDC stake and data centre pipeline add mark-to-market and funding risk. AUD weakness adds to translated volatility.
- **base**: E(R)=0.0800
  - Central case as built: about 1% yield, 7% earnings growth, flat multiple. Data centre and logistics development pipeline converts on schedule and gearing stays low.
- **bull**: E(R)=0.3000
  - Data centre power-secured pipeline expands faster than expected and drives earnings upgrades to roughly 12%+ growth. The multiple re-rates upward on AI infrastructure demand, and capital partners keep funding the development work-in-progress.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 28.02 (Cat A) — GMG.AX latest close 2026-11-19 from get_price (AUD).
- `distribution_yield` = 0.0107 (Cat B) — Assumed FY26 DPS of about AUD 0.30 (from memory of issuer's flat distribution policy, not re-verified in this session) divided by the 28.02 close. ASX filing bodies are unavailable (body capture for ASX is parked), so this was not checked against a filing.
- `earnings_growth_12m` = 0.07 (Cat C) — Assumed operating EPS/NAV growth of about 7%. This is slightly below the roughly 9% operating EPS growth the issuer has guided in prior years. It is driven by development work-in-progress conversion, data centre pipeline and rental growth. Sensitivity: each ±3pts of growth moves E(R) by about ±3pts. This is not confirmed by a FY27 guidance document.
- `multiple_change` = 0.0 (Cat C) — Assumed flat P/E and NAV-premium multiple over 12 months. The stock trades at a high premium to NAV, so re-rating is neither assumed up nor down. The risk is skewed to the downside and is covered in the bear case.
- `expected_return_total` = 0.08 (Cat C) — E(R) = 1.07% yield + 7% growth + 0% multiple change, rounded to 8%.
- `risk_free_rate_source` = 0.0416 (Cat A) — FRED DTB3 3-month T-bill 4.16% on 2026-11-18, which is a USD rate. It is used as the platform-standard Rf even though the asset is AUD-denominated.
- `recent_events` = NEXTDC 9.9% stake; Q1 FY27 update (Cat A) — ASX announcements list: 'Acquisition of a 9.9% interest in NEXTDC' (price sensitive, 2026-11-08), Q1 FY27 Operational Update (2026-11-03) and AGM (2026-11-19). Headlines only, because ASX bodies are unavailable. This adds data centre exposure and capital deployment into a listed third-party stake.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_quality` = 0.7768 (Cat B) — Beta 0.78 with correlation of only 0.30 to IASP.L over 252 days, so it has low explanatory power.
- `expected_market_return_basis` = -0.0429 (Cat B) — IASP.L trailing 5.18y annualised log return of -4.29%. This depressed Rm makes the CAPM hurdle negative and flatters alpha, so alpha is a weak supporting input only.

## Key Risks
- Premium valuation multiple compression if AI and data centre sentiment reverses or global and Australian rates stay higher for longer
- Development concentration: data centre WIP and power-supply delivery, plus the new 9.9% NEXTDC stake, add execution, funding and mark-to-market risk
- High realised volatility (30% annualised) means a wide outcome distribution, and PGain of about 65% leaves considerable loss probability
- Currency-basis noise: beta and alpha are measured against GBP-denominated IASP.L with 0.30 correlation, and the Rf is a USD T-bill applied to an AUD asset
- Filing bodies for ASX are unavailable, so gearing, coverage and guidance inputs rest on headlines and prior knowledge and are not verified against FY27 filings

## Invalidation Condition
Exit if Goodman cuts or fails to reaffirm FY27 operating EPS growth guidance, or if look-through gearing rises above about 15% because of data centre or NEXTDC-related funding. Also exit if development work-in-progress yield-on-cost or completions deteriorate materially, or if the stock de-rates more than 25% from the current AUD 28.02 without a matching earnings improvement.
