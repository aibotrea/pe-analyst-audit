# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-09-16_equity_reit_v1@1.0_616db2f9a22f`
**Ticker**: C2PU.SI (Parkway Life Real Estate Investment Trust)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-09-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Parkway Life REIT delivers rare defensive healthcare income anchored by CPI-linked master leases on Singapore's premier private hospital campuses (Mount Elizabeth, Gleneagles, Parkway East), backed by IHH Healthcare as a world-class sponsor. The annualised DPU yield of 4.42% at SGD 4.00 is underpinned by a confirmed 15.1% Q1 2026 DPU beat, demonstrating durable earnings momentum from hospital rent escalations. With 1-year annualised volatility of only 10.6%, a low beta of 0.25 versus IASP.L (currency-basis caveat applies), and a CAPM alpha of 4.74%, PLife REIT exhibits superior risk-adjusted return characteristics. An OU Monte Carlo PGain of 81.5% at a 12-month horizon, combined with a structurally conservative balance sheet (~37% leverage), supports an above-average conviction rating of 4.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.0723
- P-gain: 0.8145
- CAPM alpha: 0.0474
- Beta: 0.2461
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Singapore CPI falls near-zero suppressing master lease escalations to 0%; Japan nursing home rents pressured by regulatory fee caps; JPY depreciates 10-15% vs SGD eroding Japan NPI; global rate spike causes 30-40bps cap rate expansion and P/NAV de-rating; potential DPU-dilutive asset disposal (flagged in July 2026 Singapore REIT news).
- **base**: E(R)=0.0650
  - Central case: distribution yield 4.42%, DPU growth 2.0% from CPI-linked escalators, multiple change -0.4%, occupancy near 100% under master lease structure, aggregate leverage ~37%.
- **bull**: E(R)=0.1600
  - Singapore CPI surprises to the upside driving stronger master lease escalations above 3%; MAS rate cuts trigger P/NAV re-rating; IHH Healthcare injects accretive hospital assets at 5.5%+ NPI yield; Japan nursing home acquisitions accretive; JPY recovers vs SGD.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0442 (Cat A) — Q1 2026 DPU of SGD 0.0442 per unit reported (Business Times, 30 Apr 2026); annualised at 4x = SGD 0.1768; implied trailing yield = SGD 0.1768 / SGD 4.00 = 4.42%. Observed published figure.
- `dpu_growth` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. reflecting CPI-linked rent review escalators in Singapore hospital master leases (~1.5-2.0% per annum) plus modest contribution from Japan nursing home revenue-linked rents, net of JPY/SGD FX drag. Sensitivity tested in bear and bull scenarios.
- `multiple_change` = -0.004 (Cat C) — Net multiple change of -0.4% over 12-month horizon, reflecting higher-for-longer rate environment partially offset by persistent healthcare-sector valuation premium. Central case assumption; sensitivity reflected in scenario analysis.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. Currency basis may cause the 0.246 beta to understate or overstate true APAC healthcare REIT systematic sensitivity.
- `aggregate_leverage` = 0.37 (Cat B) — Aggregate leverage estimated at ~35-37% based on third-party analysis citing PLife REIT strong balance sheet (Yahoo Finance, Oct 2025). Derived estimate pending direct confirmation from issuer filings. Well within Singapore MAS 50% regulatory limit.
- `sponsor_commitment` = IHH Healthcare Berhad (Cat A) — IHH Healthcare Berhad is the anchor sponsor and master lessee of Singapore hospital assets (Mount Elizabeth, Gleneagles, Parkway East). Master lease obligations are publicly filed with SGX and directly observable.

## Key Risks
- Singapore CPI deceleration would directly suppress CPI-linked master lease rent escalations, compressing DPU growth below the 2.0% base assumption
- Sustained JPY/SGD depreciation erodes Japan nursing home portfolio cash flows (approximately 40% of NPI), creating a structural FX drag on distributions
- Higher-for-longer global interest rates may expand cap rates and compress P/NAV multiples, reducing the price return component of E(R)
- July 2026 SGX news flagged potential asset disposals among Singapore REITs that may impact dividends — specific applicability to C2PU.SI requires monitoring each reporting period
- No primary issuer filings available in the data store for C2PU.SI at this as_of date; aggregate leverage, AFFO coverage, and WALE estimates are sourced from third-party commentary rather than primary filings, introducing Category B data risk to qualitative gate assessments

## Invalidation Condition
Exit the position if annualised DPU growth turns negative for two consecutive reporting periods indicating failure of the CPI-escalator mechanism or adverse rent review outcome; or if aggregate leverage rises above 45% of deposited property value approaching the MAS regulatory limit; or if IHH Healthcare reduces its master lease commitment on Singapore hospitals or its unitholding in PLife REIT falls below 35%; or if Japan nursing home NPI yield contracts below 4.5% per annum reflecting sustained regulatory fee-cap pressure on nursing operators.
