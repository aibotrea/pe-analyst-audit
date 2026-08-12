# Specialist Memo — ME8U.SI

**Memo ID**: `ME8U.SI_2026-08-12_equity_reit_v1@1.0_5ca6149b2a1c`
**Ticker**: ME8U.SI (Mapletree Industrial Trust)
**Market**: Singapore
**Sector**: Industrial/Data Centre
**As of**: 2026-08-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Mapletree Industrial Trust offers a differentiated Singapore industrial and data centre REIT with a Q1 FY2027 annualised distribution yield of approximately 6.5% at the current unit price of SGD 1.91, well above the 3.74% T-bill rate. The Temasek-linked Mapletree Investments sponsor provides pipeline optionality and demonstrated unitholder alignment, with manager fees partially paid in units. Beta of 0.31 against IASP.L (SGD/GBP currency-basis caveat applies) implies materially lower systematic risk than the broader APAC REIT universe. The OU Monte Carlo simulation returns a P(gain) of 83% at a 12-month horizon, supporting a moderate conviction position, tempered by near-term NPI headwinds flagged in Q1 FY2027 results and incomplete AFFO coverage confirmation from available filing data.

## Quantitative Chain

- E(R): 0.0751
- Std dev: 0.0784
- P-gain: 0.8299
- CAPM alpha: 0.0630
- Beta: 0.3118
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - NPI decline accelerates as rental reversions in Singapore flatten and US data centre vacancy rises amid hyperscaler capex retrenchment. DPU coverage falls below 1.0x AFFO requiring a distribution cut of 10-15%. Aggregate leverage breaches 42%, restricting debt headroom. Cap rate expansion of 30-50bps on Singapore industrial assets driven by a global rate re-escalation shock. Multiple compresses by 5-8% from current levels.
- **base**: E(R)=0.0750
  - Central case as built in quantitative chain: annualised DPU of SGD 0.1244 (Q1 FY2027 run-rate), 1.0% forward growth, zero multiple change. Singapore industrial occupancy stable, US data centre leases hold. Leverage remains within MAS regulatory limits. Easing Singapore funding costs provide modest debt refinancing tailwind.
- **bull**: E(R)=0.1900
  - DPU growth accelerates to 3-4% on the back of positive rental reversions in Singapore hi-tech industrial parks and accretive injection of Mapletree sponsor pipeline assets. US data centre portfolio leased to new hyperscaler tenants at above-market rates. Rate cuts compress cap rates by 20-25bps, driving NAV expansion. Unit price re-rates from 52-week lows toward book value, adding 8-10% multiple expansion.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0651 (Cat A) — Q1 FY2027 DPU of SGD 0.0311 per unit (period 01/04/2026–30/06/2026) annualised to SGD 0.1244, divided by closing price of SGD 1.91 on 2026-08-12. Source: ME8U.SI 2026-07-23 CACT filings (Capital Distribution and Cash Dividend/Distribution announcements).
- `dpu_growth_1yr` = 0.01 (Cat C) — Forward DPU growth of 1.0% p.a. assumed for the base case. Reflects improving Singapore industrial occupancy (positive) offset by NPI headwinds reported in Q1 FY2027 results (REITsweek, 24 Jul 2026), potential refinancing tailwinds from easing rates, and modest accretion from US data centre exposure. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Zero multiple change assumed in base case. Unit price near 52-week lows with no near-term re-rating catalyst identified; valuation broadly fair at current yield spread. Sensitivity tested in bear/bull scenarios.
- `aggregate_leverage` = 0.39 (Cat B) — MIT's aggregate leverage estimated at approximately 38-40% based on recent public disclosures and analyst commentary. Precise figure not available from truncated filing bodies; derived from historical reporting range. Within MAS 45% standard limit (50% with credit rating). Flagged as Category B pending confirmation from full financial statements.
- `us_data_centre_exposure` = 0.26 (Cat B) — US data centre assets estimated at approximately 26% of portfolio AUM based on publicly known MIT portfolio composition. This introduces USD/SGD currency risk and US commercial real estate rate sensitivity as a sub-portfolio risk factor.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP.L 5-year annualised return of -4.38% reflects cumulative GBP FX and APAC REIT drawdown effects and should not be interpreted as a standalone Rm signal.

## Key Risks
- NPI compression: Q1 FY2027 results showed declining net property income despite Singapore occupancy improvements, suggesting cost inflation or lower rental reversions — continuation would pressure DPU sustainability.
- US data centre concentration risk: ~26% of portfolio is US-domiciled data centre assets, exposing MIT to USD/SGD currency movements and US commercial real estate rate cycles.
- Higher-for-longer interest rates: Aggregate leverage of ~38-40% means refinancing risk is moderate; any reversal in Singapore rate easing expectations compresses the yield spread and may drive further unit price weakness.
- Regulatory gearing headroom: MIT operates with limited buffer to the MAS 45% aggregate leverage limit; any asset devaluation could compress headroom and restrict new acquisitions.
- Distribution visibility gap: Filing body truncation prevented direct confirmation of AFFO coverage ratio; if payout exceeds operating cash flow, distribution sustainability is at risk in a weaker operating environment.

## Invalidation Condition
Exit signal triggered if: (1) MIT's aggregate leverage as reported in any quarterly financial statement breaches 43% (narrowing MAS regulatory buffer to under 2 percentage points); (2) declared DPU for any two consecutive quarters declines more than 10% year-on-year, indicating a structural distribution cut; (3) Singapore industrial portfolio occupancy falls below 91% for two consecutive quarters; or (4) Mapletree Investments materially reduces its unitholding below 30% without a stated rationale aligned with unitholder interests.
