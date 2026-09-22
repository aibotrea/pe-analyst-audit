# Specialist Memo — CNI.AX

**Memo ID**: `CNI.AX_2026-09-22_equity_reit_v1@1.0_f9b1428610de`
**Ticker**: CNI.AX (Centuria Capital Group)
**Market**: Australia
**Sector**: Diversified Property Funds Management / REIT
**As of**: 2026-09-22
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Centuria Capital Group (CNI.AX) is a diversified Australian property funds manager with exposure to listed REITs (industrial, office, healthcare) and unlisted property funds, trading at AUD 1.29 following a significant ~43% derating from its June 2026 peak of ~AUD 2.26. The trailing distribution yield of approximately 6.2% at current prices provides income support, and the record AUM base and FY27 expansion plans underpin the base-case 2.0% growth assumption. However, with historical volatility of 35.7% (annualised) and a sharp FY26 results-day sell-off suggesting market concern around earnings quality or forward DPS guidance, conviction is constrained. The OU Monte Carlo simulation (E(R) 8.7%, sigma 35.7%) yields a PGain of 63.8% and a base-case sim_return of 8.6%, warranting a Low conviction score after a one-step downward gate override for distribution coverage uncertainty.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.2429
- P-gain: 0.6382
- CAPM alpha: 0.0830
- Beta: 0.4041
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - RBA maintains higher-for-longer rates, further compressing cap rates and property valuations across CIP, COF and HCW managed portfolios. FUM outflows reduce management fee income. DPS cut of 15-20%, distribution yield collapses to ~5% on a lower base, driving further price derating. Office REIT (COF) structural vacancy worsens, impairing CNI's stake value. CNI share price tests AUD 0.90-1.00 support. Gearing at managed fund level breaches covenants in a tail scenario.
- **base**: E(R)=0.0870
  - Central case as built in chain: distribution yield 6.2%, DPU growth 2.0% p.a., modest +0.5% multiple reversion contribution. Record AUM momentum continues into FY27, management fees grow modestly. RBA cuts 1-2x over the next 12 months, providing modest support to property valuations. Occupancy at managed REITs holds broadly stable. CNI share price consolidates around AUD 1.30-1.50.
- **bull**: E(R)=0.3200
  - RBA delivers 3+ rate cuts, materially re-rating property sector. Centuria Capital's managed AUM grows >10% from FY27 pipeline (industrial logistics, healthcare, unlisted). Distribution reinstated at prior levels (~9-10 cents), driving yield rerating. COF office portfolio stabilises with improved occupancy. CNI's deep discount to intrinsic value closes, share price recovers toward AUD 1.70-1.90. Analyst consensus upgrades from current buy ratings.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.062 (Cat A) — Trailing distribution yield of ~6.2% derived from published market commentary (Kalkine, July 2026) citing a 6.17% yield at prices consistent with the current AUD 1.29 close. Centuria Capital historically distributes ~7.5-8.5 cents per security; at AUD 1.29, implied DPS of approximately 8.0 cents equates to ~6.2%. Treated as Category A given the reference to a published, observable yield figure.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU/distribution growth assumed at 2.0% p.a. based on record AUM growth trajectory noted in September 2026 news (Kalkine: 'Record AUM and FY27 expansion plans'). Management fee income is correlated with FUM growth. Conservative assumption given elevated interest rate environment pressuring property valuations. Sensitivity: bear -1% to bull +4%.
- `multiple_change` = 0.005 (Cat C) — Assumed +0.5% contribution from multiple reversion. CNI.AX has derated significantly from ~AUD 2.26 (June 2026) to AUD 1.29 (Sep 2026), a ~43% decline. At this level, assuming modest partial recovery in sentiment with flat-to-modest rerating embedded in forward return. Sensitivity: bear -3% to bull +8%.
- `fy26_results_concern` = flagged (Cat B) — CNI.AX experienced a sharp price decline on high volume on 27 August 2026 (price dropped ~11% intraday, volume ~17.6M vs normal ~2-4M), consistent with FY26 results release. News from August 2026 cited 'rate anxiety grips REIT sector' around FY26 result. Exact DPS and AFFO coverage not confirmed from filing bodies (ASX filing bodies cross-contaminated in stored data pipeline). Distribution coverage assumed adequate but flagged as uncertainty.
- `leverage_assumption` = info_only (Cat B) — CNI.AX is a fund management entity holding stakes in listed REITs (CIP, COF, HCW) and unlisted funds. Corporate gearing at Centuria Capital level is typically modest (~20-30% LVR). Managed REITs target gearing within Australian AREIT convention (<40%). Exact corporate balance sheet gearing not confirmed from available filings but no adverse data observed. Flagged as information only.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp benchmark noise. The low correlation (0.13) versus IASP.L further limits the reliability of the beta estimate for CAPM purposes.

## Key Risks
- Higher-for-longer RBA rates compressing property cap rates, reducing portfolio valuations and triggering gearing covenant stress at managed REITs (CIP, COF), potentially reducing fee income and impairing CNI's balance sheet stakes.
- Structural decline in office demand weighing on Centuria Office REIT (COF) occupancy and asset values, with CNI holding a management stake and seed investment in the most challenged sub-sector.
- Distribution sustainability uncertainty: FY26 results triggered a significant market sell-off (high-volume price decline of ~11% on 27 August 2026), suggesting possible DPS cut or guidance reduction not fully captured in available filed data.
- AUM growth dependent on retail and institutional capital flows into unlisted property funds, which are sensitive to macro sentiment and liquidity; a prolonged property downturn could trigger redemption pressure.
- Beta estimate low reliability: 0.13 correlation with IASP.L (GBP-denominated) reflects substantial currency and sector noise, limiting CAPM signal quality. Calibration is directional only (Phase 2 limitation).

## Invalidation Condition
Exit if Centuria Capital Group announces a distribution per security reduction exceeding 15% versus the prior corresponding period for two consecutive half-year periods, or if aggregate gearing at either Centuria Industrial REIT (CIP) or Centuria Office REIT (COF) breaches 40% LVR for two consecutive reporting periods, or if AUM declines materially (more than 10%) from the FY26 record base, signalling structural FUM outflows rather than a transient rate cycle.
