# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-08-19_equity_reit_v1@1.0_532725f2afec`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-08-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
AIMS APAC REIT offers diversified Singapore and Australian industrial and logistics exposure at a trailing yield of approximately 5.9% at the current SGD 1.48 unit price, providing a meaningful spread over the 3.71% risk-free rate. The recently completed Hazelmere, Perth acquisition (Aug 2026) and the confirmed call of the S$250M 5.375% perpetual securities (redemption 1 Sep 2026) represent two concurrent catalysts: AUM expansion and capital structure simplification. Beta of 0.26 versus IASP.L (currency-basis caveat applies) indicates meaningfully lower co-movement with the broader APAC REIT universe, offering defensive characteristics. The OU Monte Carlo PGain of 80.9% at a 12-month horizon, combined with a CAPM alpha of 7.3%, supports an above-average conviction position.

## Quantitative Chain

- E(R): 0.0890
- Std dev: 0.1013
- P-gain: 0.8088
- CAPM alpha: 0.0731
- Beta: 0.2602
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Singapore industrial occupancy slips below 93% on demand softening; Australian industrial cap rates expand 50bps on RBA policy surprise or AUD weakness; S$250M perp refinancing executes at materially higher cost than assumed; DPU coverage falls below 1.0x AFFO for two consecutive half-year periods; broader S-REIT de-rating driven by higher-for-longer SGD rates compressing the yield spread vs the risk-free rate.
- **base**: E(R)=0.0890
  - Central case: forward DPU ~SGD 0.0875 per unit (yield 5.91% at SGD 1.48), organic DPU growth 2.5%, modest multiple re-rating +0.5%; gearing ~36% well within MAS 50% limit; Hazelmere acquisition accretive; perp refinancing neutral to modestly positive; occupancy stable at approximately 95%.
- **bull**: E(R)=0.2000
  - Strong Singapore industrial rental reversions of 8–10%; Australian industrial assets re-rated on tight Perth/Sydney vacancy; perp refinancing at significantly lower cost boosts distributable income; potential AIMS sponsor pipeline injection of additional high-yield industrial assets; S-REIT sector re-rating as SGD rates fall faster than expected, compressing cap rates and lifting NAV.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0591 (Cat A) — Forward DPU of approximately SGD 0.0875 per unit annualised divided by closing price of SGD 1.48 on 2026-08-19. DPU estimate anchored to publicly disclosed FY2025 actuals (~8.60 Scts) and corroborated by May 2026 media headline referencing steady DPU growth. Observed closing price is Category A; the forward DPU estimate is Category B.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth assumption of 2.5% p.a. reflecting: (1) Singapore industrial rental reversion in a tight vacancy environment, (2) incremental income from the completed Hazelmere, Perth Australian industrial acquisition (O5RU.SI 2026-08-05 ANNC — Completion of Acquisition 398 Bushmead Road and 286 Stirling Crescent), and (3) partial offset from higher cost of refinancing the S$250M 5.375% perpetual securities called for 1 Sep 2026 (O5RU.SI 2026-07-31 CACT). Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest positive cap-rate re-rating assumption of +0.5% contribution to total return, reflecting a declining SGD interest rate environment and improving sentiment toward smaller-cap S-REITs as per July 2026 market commentary. Central case assumption; subject to reversal if rates remain elevated.
- `perp_call_deleveraging` = positive (Cat A) — S$250,000,000 5.375% Subordinated Perpetual Securities called for mandatory early redemption on 1 Sep 2026 (O5RU.SI 2026-07-31 CACT). Redemption removes a costly hybrid instrument and is expected to modestly reduce the effective cost of capital when refinanced at prevailing lower rates. Observed corporate action, Category A.
- `equity_fundraising_deployed` = accretive (Cat B) — Equity fund raising proceeds confirmed deployed as of 5 Aug 2026 (O5RU.SI 2026-08-05 ANNC — Use of Proceeds). Capital was directed toward the completed Hazelmere, Perth industrial acquisition. Accretiveness is a Category B estimate pending formal earnings disclosure; no body details available on specific yield.
- `leverage_gearing` = 0.36 (Cat B) — Estimated aggregate leverage of approximately 36% of deposited property value, consistent with AA REIT's historically disclosed gearing range of 33–37%. The S$250M perp call and equity raising activity have opposing effects. Estimate is Category B pending the next formal MAS-compliant gearing disclosure. Singapore regulatory limit is 50%.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency basis noise.

## Key Risks
- Perp securities refinancing risk: the S$250M 5.375% perp called for 1 Sep 2026 must be refinanced or replaced; a materially higher cost of substitute funding would reduce distributable income.
- Singapore industrial demand softening: any reversal in the tight vacancy environment would suppress rental reversions and DPU growth assumptions.
- Australian asset concentration and currency risk: the Hazelmere acquisition and broader Australian portfolio introduce AUD/SGD FX translation risk and exposure to Perth industrial market cycles.
- Higher-for-longer SGD interest rates compressing the yield spread and triggering cap-rate expansion that erodes NAV.
- Smaller-cap S-REIT liquidity risk: O5RU.SI trades at lower daily volumes than large-cap S-REITs, amplifying price volatility in a risk-off market environment.

## Invalidation Condition
Exit if reported MAS aggregate leverage exceeds 45% of deposited property value for two consecutive disclosure periods, or if DPU coverage falls below 1.0x AFFO for two consecutive half-year periods, or if the S$250M perp refinancing is executed at a cost exceeding 6.5% annualised, or if Singapore industrial portfolio occupancy declines below 91% on a sustained basis.
