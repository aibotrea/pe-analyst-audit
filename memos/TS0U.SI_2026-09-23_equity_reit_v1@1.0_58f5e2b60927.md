# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-09-23_equity_reit_v1@1.0_58f5e2b60927`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified Office/Hospitality
**As of**: 2026-09-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
OUE REIT offers a headline distribution yield of approximately 7.3% at SGD 0.345, providing a meaningful nominal income return for a Singapore-listed office and hospitality REIT. The proposed divestment of Crowne Plaza Changi Airport as an Interested Person Transaction introduces governance uncertainty and near-term income composition risk, and the elevated aggregate leverage (Rule 704(31) disclosure filed July 2026) constrains financial flexibility. The low CAPM beta of 0.29 versus IASP.L likely reflects both genuine defensive characteristics and SGD/GBP currency-basis noise; CAPM alpha of 5.87% is supportive but inherits the same noise. The OU Monte Carlo PGain of 69.5% and above-average CAPM alpha are partially offset by high annualised volatility of 20.9%, leading to a conviction score of 2 (Low) after a one-step management-alignment gate override.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1419
- P-gain: 0.6949
- CAPM alpha: 0.0587
- Beta: 0.2892
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Crowne Plaza Changi Airport divestment falls through or completes at a material discount to valuation, triggering a rights issue or substantial gearing breach near the 45% regulatory limit. DPU for 2H2026 cut by 20%+ as distributions are diverted to debt repayment. Singapore office market softens with vacancy rising 2–3 percentage points. Cap rate expansion of 50bps compresses NAV by ~12%. Manager continues to dilute unitholders via fee-in-units issuance in a falling price environment.
- **base**: E(R)=0.0730
  - Central case as modelled: Crowne Plaza Changi Airport divestment completes at announced price, reducing gearing to a more comfortable range. Annualised DPU of ~SGD 0.0252/unit maintained with 0.5% growth. Singapore CBD office occupancy stable at current levels. Cap rates flat. Multiple change -0.5% offsetting growth. Yield spread over T-bill of ~3.3% remains supportive.
- **bull**: E(R)=0.1900
  - Divestment completes at a premium, materially reducing gearing and enabling a special distribution. Singapore office demand strengthens with Grade A CBD occupancy improving, supporting DPU growth of 3–4%. OUE sponsor injects accretive commercial assets into the REIT at yields above 6%. Market re-rates OUE REIT toward peer group at lower yield spread, driving price appreciation of 10–12% above the distribution return.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.073 (Cat A) — Annualised DPU of SGD 0.0252/unit derived from 1H2026 declared distribution of SGD 0.0126/unit (period 1 Jan–30 Jun 2026), divided by current price SGD 0.345. Source: TS0U.SI 2026-07-22 Cash Dividend/Distribution announcement (SGX ref SG260722DVCAIKB8). Yield = 0.0252 / 0.345 = 7.30%.
- `dpu_growth_assumption` = 0.005 (Cat C) — Forward DPU growth of 0.5% p.a. assumed. Post-divestment of Crowne Plaza Changi Airport (announced 2026-06-25), the portfolio transitions to a more pure-play Singapore office REIT. Growth reflects modest positive reversionary rent potential in Singapore CBD office market, partially offset by loss of hotel income contribution and potential distribution dilution from manager base fee paid in new units (TS0U.SI 2026-07-27 fee-in-units announcement). Sensitivity tested in scenario analysis.
- `multiple_change_assumption` = -0.005 (Cat C) — Assumed -0.5% p.a. cap rate/multiple drag. Elevated gearing level (Rule 704(31) disclosure filed 2026-07-31 under SGX Listing Manual aggregate leverage rules) and the IPT nature of the Crowne Plaza Changi Airport divestment to a related party create overhang on valuation re-rating. Singapore commercial REIT sector trades at a discount to NAV. Sensitivity tested in scenario analysis.
- `cpca_divestment_status` = pending_egm_approval (Cat A) — Proposed divestment of Crowne Plaza Changi Airport announced 25-Jun-2026 as an Interested Person Transaction and Interested Party Transaction. EGM convened 13-Aug-2026 with Circular to Unitholders issued. SIAS dialogue session held 26-Aug-2026. As of 23-Sep-2026, 3Q2026 business update release date announced but results not yet published. Divestment proceeds and final gearing impact remain pending completion.
- `aggregate_leverage_estimate` = elevated_above_40pct (Cat B) — OUE REIT filed Rule 704(31) Listing Manual disclosure on 2026-07-31, which pertains to aggregate leverage ratio under SGX regulations (≤50% limit). Filing confirms leverage disclosure trigger. Exact ratio not extractable from headline alone (body attachment not parsed). Estimated above 40% based on known pre-divestment asset base. Singapore regulatory limit is 45% (or 50% with credit rating). Divestment of Crowne Plaza Changi Airport is expected to reduce total assets, and the net gearing impact depends on disposal proceeds relative to debt repaid.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. The low beta of 0.289 partly reflects currency basis noise between SGD and GBP rather than purely OUE REIT's underlying property market sensitivity. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Crowne Plaza Changi Airport divestment completing at a discount to book value or failing to complete, leading to sustained elevated gearing above the Singapore 45% regulatory threshold and potential forced asset sales or equity issuance.
- Continued manager base-fee payment in newly issued units erodes NAV per unit in a stagnant-to-declining price environment, structurally disadvantaging long-term unitholders.
- Singapore office market softening — a deterioration in CBD Grade A occupancy or rental reversions turning negative would reduce distributable income, particularly as the portfolio becomes more concentrated in office post-hospitality disposal.
- Higher-for-longer US interest rates keeping Singapore interbank rates elevated, compressing the DPU yield spread versus the 4.0% T-bill and sustaining the discount to NAV.
- IPT governance risk: the EGM-approved Crowne Plaza Changi Airport sale to a related party raises conflict-of-interest concerns; if unitholder scrutiny (SIAS dialogue) reveals pricing irregularities, regulatory or reputational consequences could follow.

## Invalidation Condition
Exit if (1) aggregate leverage ratio breaches 45% for two consecutive reporting periods without a credible and approved deleveraging plan, (2) the Crowne Plaza Changi Airport divestment is aborted or completed at more than 10% below the announced disposal price, (3) annualised DPU falls below SGD 0.020/unit implying a greater than 20% DPU cut from the 1H2026 run-rate, or (4) any SGX regulatory action or MAS investigation is initiated in connection with the IPT divestment transaction.
