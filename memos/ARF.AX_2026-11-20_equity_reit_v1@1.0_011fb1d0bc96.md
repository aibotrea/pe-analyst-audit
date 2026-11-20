# Specialist Memo — ARF.AX

**Memo ID**: `ARF.AX_2026-11-20_equity_reit_v1@1.0_011fb1d0bc96`
**Ticker**: ARF.AX (Arena REIT)
**Market**: Australia
**Sector**: Social Infrastructure (Childcare/Healthcare)
**As of**: 2026-11-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Arena REIT offers Australian social-infrastructure exposure (early learning and healthcare) with a guided FY27 yield of about 7.2%, well above the 4.2% T-bill rate. The yield is offset by tenant-credit uncertainty: Edge Early Learning is in administration and a Goodstart transaction has been announced. Realised 12-month volatility is 37% (OU simulated standard deviation 25%), so PGain is only 62% despite a positive expected return of about 8%. The base score of 3 is cut one step to 2 because of the unresolved concentration and tenant-credit issue. A $50M buyback and the raised FY27 guidance are mitigants. The data gaps on gearing and AFFO coverage and the weak beta fit against IASP.L (currency-basis caveat) argue for a small position.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.2520
- P-gain: 0.6228
- CAPM alpha: 0.0977
- Beta: 0.7203
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - The Edge Early Learning administration ends in lease rejections or rent cuts, and Goodstart or other operators do not take up the vacated centres on equivalent terms. FY27 distribution falls below the 20c guidance, valuers widen childcare cap rates by 25-50bps in a higher-for-longer rate or stagflation regime, and the 40% rally reverses toward the October low of about 2.00.
- **base**: E(R)=0.0800
  - Central case as built in the chain. FY27 distribution of about 20c is delivered (7.2% yield), growth is 2% from rent escalators, and affected centres are re-tenanted or transferred with limited income loss. Multiples de-rate slightly after the recent rally.
- **bull**: E(R)=0.2600
  - The administration resolves cleanly with Goodstart or other quality operators assuming the leases. The $50M buyback is accretive at a discount to NAV, and AU rate relief lets childcare cap rates compress. Distribution growth reaches 4%+ and the multiple re-rates, which adds to the 7%+ yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 2.79 (Cat A) — ARF.AX closing price on 2026-11-20 in AUD, from get_price.
- `distribution_yield` = 0.0717 (Cat B) — FY27 distribution guidance of about 20 cents per security, taken from news headlines (Kalkine, 2026-11-04 and 2026-11-18), divided by the 2.79 AUD price. The ASX 'FY2027 Distribution Guidance Update' (2026-11-02) was identified by headline only. The stored filing body was mismatched and belonged to another issuer, so it was not used. The guidance figure is not verified against the primary document.
- `dpu_growth` = 0.02 (Cat C) — Assumed 2% annual distribution and NAV growth from fixed or CPI-linked rent escalators and modest development or acquisition contribution. Sensitivity is in scenario_analysis (bear 0%, bull 4%+).
- `multiple_change` = -0.0117 (Cat C) — Assumed small de-rating. The price rallied from about 1.99 (2026-10-05) to 2.79 (+40%) after the tenant-administration and guidance news, so some give-back is allowed for. Residual so that E(R) is about 8.0%: 7.17% yield + 2.0% growth - 1.17% multiple.
- `expected_return_build` = 0.08 (Cat C) — E(R) = yield 7.17% (B) + growth 2.0% (C) + multiple change -1.17% (C) = about 8.0%. This is the base_return input to the OU Monte Carlo.
- `risk_free_rate` = 0.0416 (Cat A) — FRED DTB3 3-month US T-bill rate of 4.16% on 2026-11-19. It is a USD rate and is used as the platform-standard Rf. The AUD risk-free rate would differ.
- `expected_market_return` = -0.0407 (Cat B) — Trailing annualised log return of IASP.L over 1260 days (about 5.2 years, 1305 observations). The GBP basis adds FX noise, and the figure is negative so CAPM required return is below Rf.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_quality` = 0.7203 (Cat B) — 252-day beta of 0.72 against IASP.L with a correlation of only 0.23, so the estimate is statistically weak. The CAPM alpha of 9.8% is a supporting input only.
- `filing_data_gap` = disclosed (Cat B) — Stored filing bodies for ARF.AX returned text from other issuers (PEXA, Omni Bridgeway, Dexus Convenience Retail REIT, Brambles and others), so no gearing, AFFO coverage, WALE or occupancy figures were extracted from issuer documents. ASX body capture is also parked. Qualitative gates rely on headlines and news only.

## Key Risks
- Tenant credit and concentration: the Edge Early Learning administration may lead to lease disclaimers, rent reductions or re-tenanting vacancy, and the Goodstart transaction terms were not verified from issuer documents.
- Rate and cap-rate risk: AU interest-rate rises and falling property prices (noted in market commentary) could widen childcare cap rates and pressure NAV and the unit price.
- Price momentum and volatility: the price is up about 40% since early October, realised volatility is 37%, and the OU distribution is wide (PGain 62%), so a give-back is plausible.
- Data and model limitations: stored filings were mismatched, so gearing, AFFO coverage, WALE and occupancy are unverified. Beta has a correlation of only 0.23 to the GBP-denominated IASP.L, and the Rf is a USD T-bill. Phase 2 calibration is directional only, not a formal backtest.

## Invalidation Condition
Exit if the Edge Early Learning administration leads to material lease rejections or rent reductions that push FY27 distribution guidance below 20 cents per security, or if reported gearing rises above the 40% Australian convention, or if AFFO coverage falls below 1.0x for two consecutive reporting periods, or if the unit price closes below about 2.00 AUD (the October low) without a fundamental explanation.
