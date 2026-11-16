# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-11-16_equity_reit_v1@1.0_8d492c7f6dae`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Residential/Lifestyle Communities
**As of**: 2026-11-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
INA trades at AUD 5.30, a premium to the reported AUD 5.25 Warburg Pincus proposal. The stock has re-rated about 45% from its August low, so most of the contest value appears to be priced in. The E(R) build of 4.2% is yield 3.2% plus growth 4% less a 3% multiple contraction. The OU Monte Carlo gives a 12-month return of 4.1% against a 24.6% standard deviation, so PGain is only 56.6%. Positive CAPM alpha (5.2%, with the currency-basis caveat) reflects a negative IASP.L market return and does not add much confidence. A one-step gate reduction for unverifiable distribution coverage and gearing takes conviction from 3 to 2, which supports a small position.

## Quantitative Chain

- E(R): 0.0420
- Std dev: 0.2460
- P-gain: 0.5660
- CAPM alpha: 0.0520
- Beta: 0.6230
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2800
  - Takeover contest collapses and the bid premium unwinds, with the price reverting toward the AUD 3.7-4.3 range of mid-2026. A rate shock or stagflation pathway (higher-for-longer Australian rates, wider cap rates, weaker settlements in development) compresses the multiple by 25%+. DPU growth is nil and coverage is tight.
- **base**: E(R)=0.0420
  - Central case as built in the chain: yield 3.2%, growth 4%, multiple contraction of 3% as the price drifts toward a final agreed or competing bid level near AUD 5.25-5.40, and no major change in rates.
- **bull**: E(R)=0.2000
  - Competitive bidding between Warburg Pincus and Avid lifts the final scheme price to ~AUD 5.80-6.00 and the deal is implemented. Alternatively, the standalone case re-rates on strong settlements and rental growth, with the 3.2% yield and 4% growth added to a 10%+ multiple gain.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 5.3 (Cat A) — INA.AX latest close AUD 5.30 on 2026-11-16 (get_price). The 1-year monthly history shows a rise from about AUD 3.66 (Aug 2026) to AUD 5.30, consistent with takeover-driven re-rating.
- `distribution_yield` = 0.032 (Cat B) — Approximate forward distribution yield (~17c per security on a AUD 5.30 price). This is my estimate from memory of recent DPS guidance. No issuer filing with DPS was retrievable, because the stored filing bodies were mismatched to other issuers. Sensitivity: +/-0.5pp moves E(R) by the same amount.
- `growth_component` = 0.04 (Cat C) — Assumed annual earnings/DPU growth of about 4%, from rental growth in lifestyle communities plus development settlements, below consensus-type double-digit EPS growth to be conservative. No verified guidance was available. Tested in the bear and bull scenarios.
- `multiple_change` = -0.03 (Cat C) — Assumed 3% multiple contraction over 12 months, because the price (5.30) already sits above the reported revised AUD 5.25 Warburg Pincus proposal and embeds bid premium. This is a model assumption. If a bid fails, de-rating could be much larger.
- `expected_return_build` = 0.042 (Cat C) — E(R) = yield 3.2% + growth 4.0% + multiple change -3.0% = 4.2%.
- `takeover_situation` = active (Cat A) — ASX headlines (INA.AX 2026-11-12 'Receipt of non-exclusive proposal from Warburg Pincus'; 2026-11-15 'AVID exercises matching right and Peet ACCC determination', both Takeover/Scheme Announcements) and news (Mingtiandi 2026-11-02, Motley Fool 2026-09-28, Kalkine 2026-10-19) indicate a live contest. The stored filing bodies for these rows contained unrelated issuers' text (FortifAI, Pacific Edge, etc.) and were ignored as off-topic. The headline attribution for the Avid/Peet item is uncertain. Deal terms were not verified from primary documents.
- `risk_free_rate_source` = 0.0413 (Cat A) — US 3-month T-bill (DTB3) 4.13% on 2026-11-13.
- `expected_market_return` = -0.041 (Cat B) — IASP.L trailing 5.18-year annualised log return of -4.10% (calculate_benchmark_return, 1260-day lookback). It is GBP-denominated and absorbs FX effects.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_value` = 0.623 (Cat B) — 252-day beta vs IASP.L with correlation of only 0.20, so the estimate is low-confidence and probably understates INA's true market sensitivity.
- `leverage_gate_basis` = unverified (Cat C) — Gearing was not retrievable from stored filings. I assume it is below the AU convention of 40%, based on INA's historical low-30s% gearing. Needs confirmation in the FY26 results.

## Key Risks
- Takeover failure or withdrawal would remove the bid premium. The price could revert toward AUD 3.7-4.3, with downside of 20-30%.
- Source data gaps: stored filing bodies were mismatched to other issuers, and DPS, AFFO coverage and gearing were not verified. The headline attribution of the Avid/Peet item is uncertain.
- High volatility of 36% annualised, plus a low beta correlation (0.20) to IASP.L. The currency-basis caveat means beta and CAPM alpha are noisy.
- Australian rate and cap-rate risk, and cyclical exposure of development settlements and home-price sentiment. The 5-year IASP.L return is negative, so the Rm used in alpha is depressed.
- Calibration limitation: this is a directional signal, not a formal vintage-disciplined backtest. Macro series other than DTB3 were not consulted.

## Invalidation Condition
Exit if the board rejects or Warburg Pincus and Avid both withdraw so the contest ends without a transaction and the price falls below about AUD 4.60, or if FY26/1H27 reporting shows gearing above 40% or distribution coverage below 1.0x operating earnings for two consecutive periods. Also exit if the price rises well above any final agreed offer without matching fundamentals.
