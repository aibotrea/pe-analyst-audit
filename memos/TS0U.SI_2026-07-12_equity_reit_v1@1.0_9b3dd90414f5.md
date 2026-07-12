# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-07-12_equity_reit_v1@1.0_9b3dd90414f5`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified (Hospitality & Commercial)
**As of**: 2026-07-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
OUE REIT (TS0U.SI) is a Singapore-listed diversified REIT with mixed hospitality and commercial assets managed under OUE Limited (Lippo Group-affiliated). The trailing DPU yield of approximately 6.1% at the current SGD 0.36 price provides a modest spread over the 3.69% 3-month T-bill rate. The OU Monte Carlo simulation generates a 12-month expected return of 7.0% with a PGain of 68%, which ordinarily supports a mid-range conviction. However, two material governance concerns — an unresolved director litigation (announced May 2026) and the IPT classification of the proposed Crowne Plaza Changi Airport divestment (announced June 2026) — trigger a one-step downward gate override, resulting in a conviction score of 2 (Low). The S$150M notes redemption in June 2026 is a positive deleveraging signal, but the 1H2026 financial results (period ended 30 June 2026) are pending and may materially alter the gearing and DPU coverage picture.

## Quantitative Chain

- E(R): 0.0710
- Std dev: 0.1501
- P-gain: 0.6802
- CAPM alpha: 0.0567
- Beta: 0.2860
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Crowne Plaza Changi Airport divestment fails or is completed at a price below NAV (loss on disposal), gearing remains elevated above 42%, DPU cut of 10-15% as hospitality income drops out ahead of replacement income, director litigation results in material financial liability or management distraction, cap rate expansion of 30bps in Singapore commercial segment driven by prolonged higher-for-longer interest rates, distribution yield spread narrows to zero versus 3-month T-bill.
- **base**: E(R)=0.0710
  - Central case: Crowne Plaza Changi Airport divestment completes at announced terms, gearing falls to approximately 38% post-proceeds, DPU broadly stable with +0.5% growth from commercial segment rental uplift, S$150M notes redemption improves interest coverage, slight positive re-rating of +0.5% as balance sheet quality improves, Singapore commercial occupancy held at ~90%.
- **bull**: E(R)=0.1800
  - Divestment proceeds redeployed into a yield-accretive commercial acquisition at 6%+ NPI yield, gearing reduced to below 35%, DPU growth accelerates to 3-4%, Singapore office market tightens driving rental reversions at OUE Bayfront, director litigation resolved without financial liability, re-rating of 8-10% as discount to NAV narrows materially, hospitality recovery in Singapore boosts Mandarin Orchard RevPAR.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.061 (Cat A) — Implied trailing DPU yield derived from latest market price of SGD 0.360 (trade date 2026-07-10) and publicly available FY2025 DPU of approximately SGD 0.0218. Observed closing price is a Category A input; DPU sourced from issuer-published distributions.
- `dpu_growth_3yr` = 0.005 (Cat C) — Forward DPU growth set at +0.5% p.a. reflecting minimal organic upside. Portfolio is undergoing asset recycling (proposed divestment of Crowne Plaza Changi Airport, filed 2026-06-25), reducing hospitality income concentration. Commercial segment (OUE Bayfront, Lippo Plaza Shanghai) provides partial offset. Conservative assumption given IPT divestment complexity and pending 1H2026 results. Sensitivity: bear case assumes 0% growth, bull case assumes 1.5%.
- `multiple_change` = 0.005 (Cat C) — Slight positive re-rating assumption of +0.5% from divestment-driven balance sheet improvement following redemption of S$150M 3.95% notes (June 2026) and potential gearing reduction from Crowne Plaza Changi Airport divestment proceeds. Flat-to-slightly-positive assumption; sensitivity: zero in base, negative in bear.
- `gearing_estimate` = 0.4 (Cat B) — Estimated aggregate leverage of approximately 40% based on publicly known OUE REIT capital structure and the 2026-06-02 redemption and cancellation of S$150,000,000 3.95% Notes due 2026 (TS0U.SI 2026-06-02 ANNC). Within Singapore MAS 45% regulatory limit. Exact post-redemption figure to be confirmed in 1H2026 results (due after period ended 30 June 2026, as per TS0U.SI 2026-06-22 ANNC). Derived estimate classified Category B.
- `litigation_director_risk` = flagged (Cat A) — Update on Litigation against Director filed 2026-05-11 (TS0U.SI 2026-05-11 ANNC). Outcome unknown; classified as observed governance risk. Full body of PDF not captured; headline and filing reference are Category A observable facts. Risk incorporated in management_alignment gate override.
- `cpca_divestment` = flagged (Cat A) — Proposed Divestment of Crowne Plaza Changi Airport announced 2026-06-25 as both an Interested Person Transaction (IPT) and Interested Party Transaction (TS0U.SI 2026-06-25 ANNC). IPT classification introduces related-party governance risk. Financial terms (sale price, NAV impact, gearing delta) pending 1H2026 results disclosure.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Low correlation (0.15) and low beta (0.29) may in part reflect SGD/GBP currency divergence rather than genuine low systematic risk.

## Key Risks
- Director litigation (TS0U.SI 2026-05-11 ANNC) outcome unknown; adverse ruling could impose financial liability on the manager and damage unitholder confidence.
- Crowne Plaza Changi Airport divestment is classified as an IPT — if completed below NAV or on unfavourable terms, it would be DPU-dilutive and destroy capital; 1H2026 results may reveal financial impact.
- Higher-for-longer SGD interest rates compressing the yield spread versus T-bills; OUE REIT has historically carried meaningful floating-rate debt exposure.
- High annualised volatility of 22.1% (252-day) relative to the DPU yield cushion of 6.1% leaves limited margin of safety against price drawdown; OU model std_dev of 15.0% implies meaningful downside scenarios.
- Concentration risk: OUE Bayfront and Lippo Plaza (Shanghai) represent significant commercial exposure; any Singapore office market softening or China macroeconomic headwinds could materially reduce NPI.

## Invalidation Condition
Exit if: (1) 1H2026 results disclose gearing above 43% post-Crowne Plaza divestment proceeds, or DPU coverage falling below 1.0x AFFO for any two consecutive reporting periods; (2) director litigation results in a financial penalty or management removal; (3) Crowne Plaza Changi Airport divestment is completed at a price materially below appraised NAV (greater than 5% discount), confirming value-destructive related-party dynamics; or (4) annualised DPU is cut by more than 10% from the FY2025 base.
