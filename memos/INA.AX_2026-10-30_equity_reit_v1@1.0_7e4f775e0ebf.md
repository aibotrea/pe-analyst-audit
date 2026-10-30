# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-10-30_equity_reit_v1@1.0_7e4f775e0ebf`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Residential/Manufactured Housing & Communities (Land Lease and Holiday)
**As of**: 2026-10-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
INA.AX is a land-lease communities operator now trading on takeover speculation. Warburg Pincus and AVID (reportedly backed by Brookfield and Mubadala) have lodged competing proposals, and the price rose about 11.6% in the week to 2026-10-30. The OU Monte Carlo gives a 12-month simulated return of about 4.6% with a standard deviation of about 24.6%, so PGain is 57%. CAPM alpha is positive at about 6.8%, but it is inflated by the negative IASP.L five-year return and carries currency-basis noise. Conviction is moderate. The return is a roughly symmetric bet on whether a deal completes at a higher price or collapses back to pre-bid levels, and fundamentals could not be verified from filings.

## Quantitative Chain

- E(R): 0.0470
- Std dev: 0.2463
- P-gain: 0.5739
- CAPM alpha: 0.0683
- Beta: 0.7007
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1400
  - Bidders withdraw or the board rejects the proposals, and the bid premium unwinds to about AUD 4.6-4.7. Higher-for-longer rates and a risk-off market (stagflation-style shock) widen land-lease cap rates by 25-50bps, and development settlements slow. The distribution yield stays near 2%, which does not offset the unwind.
- **base**: E(R)=0.0470
  - Central case as built in the chain: 2.2% yield, 5% growth, and a 2.5% give-back of the bid premium. The contest keeps the price supported without a final agreed price materially above current levels.
- **bull**: E(R)=0.1500
  - The competing bidders (Warburg Pincus, AVID with Brookfield and Mubadala) raise offers again and the board recommends a scheme at a further premium to AUD 5.31. Alternatively, the stock re-rates on strong FY27 settlements and development margins.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 5.31 (Cat A) — INA.AX close on 2026-10-30 (AUD 5.31). The price rose about 11.6% from AUD 4.76 on 2026-10-23, before the AVID indicative proposal on 2026-10-25. The rise reflects the AVID proposal and the improved Warburg Pincus proposal.
- `distribution_yield` = 0.022 (Cat B) — Approximate trailing distribution of about 11-12 cents per security on a price of AUD 5.31. This is my estimate. I could not verify it from the stored filings, because the returned filing bodies belonged to other issuers. Treat the figure as indicative.
- `earnings_growth` = 0.05 (Cat C) — Assumed organic per-security growth from land-lease rent escalation, home settlements and development margins. It is below the FY26 reported profit growth of about 45% (Kalkine headline, 2026-08-25). Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.025 (Cat C) — Assumed partial give-back of the bid premium. The probability-weighted outcome sits between a completed deal (modestly above the current price) and a failed process (reversion toward AUD 4.6-4.8). Sensitivity is covered in the scenarios.
- `expected_return_build` = 0.047 (Cat C) — E(R) = yield 2.2% (B) + growth 5.0% (C) + multiple change -2.5% (C) = 4.7%.
- `historical_volatility` = 0.362 (Cat B) — 252-day annualised volatility from stored prices (262 observations). It is inflated by the 2026-10-15/16 selloff to about AUD 3.96 and the subsequent takeover-driven gaps. It overstates ordinary REIT risk but fits the current event-driven regime.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill rate of 4.0% on 2026-10-29. It is a USD rate used as the risk-free proxy for an AUD asset, so it adds some currency-basis noise.
- `expected_market_return` = -0.0475 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (1,304 observations, lookback 1,260). IASP.L is GBP-denominated, so the figure absorbs FX co-movement.
- `takeover_situation` = active (Cat A) — ASX announcements for INA: indicative proposal from AVID (2026-10-25), improved proposal from Warburg Pincus (2026-10-27), trading pause and a response to media speculation (2026-10-28). News reports a roughly A$3.2bn AVID offer backed by Brookfield and Mubadala. I could not verify per-security terms or board response from the filing bodies.
- `filing_body_gap` = disclosed (Cat B) — The stored filing bodies for INA.AX (2026-10-19 to 2026-10-30) contained text from unrelated issuers, such as CZR, CD2, RHI and Bellevue. I excluded them. Gearing, AFFO coverage, WALE and top-asset concentration were not verified from filings, so the qualitative gates are marked 'info'.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Binary takeover outcome: if the proposals lapse or the board rejects them, the price could revert to AUD 4.6-4.8, and the sharp 2026-10-15/16 drop to about AUD 3.96 shows the downside volatility.
- Fundamental data gap: gearing, AFFO coverage, WALE and asset concentration were not verified, because the stored filing bodies belonged to unrelated issuers. The gates are therefore marked 'info'.
- Volatility of 36% is event-distorted and the OU Monte Carlo may be unreliable for a takeover-driven price. Beta of 0.70 has a correlation of only 0.23 with IASP.L, and a currency-basis caveat applies.
- Rates and macro: the 4.0% USD T-bill rate and a negative 5-year IASP.L return mean a higher-for-longer or stagflation scenario could widen cap rates and slow home settlements and development.
- Calibration limitation: this is a live as_of analysis with a directional signal rather than a formal backtest. No point-in-time vintage discipline applies yet.

## Invalidation Condition
Exit if the INA board rejects or the bidders withdraw all proposals and the price falls below about AUD 4.70, which would remove the takeover premium. Also exit if the disclosed gearing exceeds 40%, AFFO coverage of distributions falls below 1.0x for two consecutive reporting periods, or settlements and development margins deteriorate materially at the next results.
