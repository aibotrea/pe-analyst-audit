# Specialist Memo — CIP.AX

**Memo ID**: `CIP.AX_2026-09-07_equity_reit_v1@1.0_652dd1e45341`
**Ticker**: CIP.AX (Centuria Industrial REIT)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-09-07
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Centuria Industrial REIT (CIP.AX) offers Australian industrial and logistics exposure at a trailing distribution yield of approximately 5.82% — a meaningful spread over the 3.75% US T-bill proxy rate — supported by an FY26 FFO of AUD 114.1m and a guidance upgrade for FY27. Beta of 0.48 versus the IASP.L benchmark (currency-basis caveat applies) indicates meaningfully lower volatility than the broader APAC REIT universe, with annualised historical volatility of 15.7%. The OU Monte Carlo simulation returns a 12-month simulated return of 7.75% with a PGain of 76.6%, and CAPM alpha of 0.081 indicates expected outperformance relative to the (negative) benchmark return environment. Conviction is moderated to 3 (Moderate) from base score 4 by a one-step qualitative override reflecting the external management structure and limited filing-body transparency on AFFO coverage.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.1066
- P-gain: 0.7664
- CAPM alpha: 0.0810
- Beta: 0.4818
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Occupancy falls below 95%, DPU growth flat at 0% as rent reviews disappoint, RBA holds rates higher-for-longer driving cap rate expansion of 25–50bps, gearing pressure forces asset sales at discounts; multiple compression drives negative total return. Bear case also captures a stagflationary macro scenario where rising AUD rates erode yield spread further.
- **base**: E(R)=0.0780
  - Central case as modelled: annualised yield 5.82%, DPU growth 2.0%, flat multiple change, occupancy stable, gearing within 33-36% range, FY27 guidance upgrade delivered.
- **bull**: E(R)=0.1750
  - RBA cuts rates, yield compression provides multiple expansion of ~5%, DPU growth accelerates to 3.5% on strong rent reversions, occupancy improves to 98%+, Centuria Capital sponsor provides accretive acquisition pipeline above 6% yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.0582 (Cat A) — Annualised DPU of AUD 0.1730 (4 x 4.325 cpu September 2026 declared distribution per ASX announcement 2026-09-03, price_sensitive=True) divided by closing price AUD 2.97 on 2026-09-07. Observed published distribution figure.
- `dpu_growth_fwd` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. estimated from FY26 results guidance upgrade (Kalkine/Motley Fool 11 Aug 2026 citing FY26 FFO of AUD 114.1m and FY27 guidance upgrade). Assumption reflects ongoing Australian industrial rental growth moderating from peak. Sensitivity: bear case uses 0%, bull case uses 3.5%.
- `multiple_change` = 0.0 (Cat C) — Flat multiple change assumed over 12-month horizon. CIP already trades near fair-value yield (~5.8%) after approximately 18% price slide over prior 6 months (Kalkine, May 2026). Assumption: no further meaningful cap rate expansion or compression. Sensitivity tested in scenario analysis.
- `fy26_ffo` = 114100000.0 (Cat B) — FY26 FFO of AUD 114.1m as reported in news coverage of CIP FY26 Results Announcement (ASX filing 2026-08-10, headline 'CIP FY26 Results Announcement'). Sourced from third-party news synthesis; filing body unavailable due to ASX pipeline mismatch. Category B due to indirect sourcing.
- `gearing_level` = ~33-36% (Cat B) — Estimated from public commentary (SimplyWallSt 12 Aug 2026 noting 'strong margins, thin cash buffer'). Historically CIP has run gearing in the 33-36% range, within Australian convention of <40%. Filing body for FY26 Financial Report was unavailable (ASX pipeline body mismatch). Treated as Category B estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis means the computed beta of 0.4818 may deviate from a true AUD-denominated property market beta. Treated as Category B input. CAPM alpha inherits the same noise. iasp currency caveat formally disclosed.

## Key Risks
- Higher-for-longer RBA rates compressing AUD yield spread and driving further cap rate expansion, eroding NTA and distributions.
- External management fee structure (Centuria Capital Group) creates potential misalignment between AUM-growth incentives and unitholder income outcomes; filing body for FY26 Financial Report was unavailable in pipeline, limiting direct AFFO coverage verification.
- Industrial demand moderation from e-commerce normalisation and potential oversupply in key east-coast logistics corridors reducing rental reversion upside.
- Elevated gearing relative to cash generation ('thin cash buffer' per market commentary) limits financial flexibility if asset valuations decline.
- Currency risk for international investors: AUD/GBP and AUD/USD volatility directly affects total return when measured in foreign currency, and also introduces noise into the IASP.L beta coefficient used in CAPM.

## Invalidation Condition
Exit or materially reduce position if CIP reports two consecutive half-year periods with DPU coverage below 1.0x AFFO, or if reported gearing breaches 40% of gross assets (Australian convention limit), or if Centuria Capital Group as responsible entity reduces its stated pipeline commitment or undertakes dilutive equity raising at a discount greater than 5% to prevailing NTA per unit.
