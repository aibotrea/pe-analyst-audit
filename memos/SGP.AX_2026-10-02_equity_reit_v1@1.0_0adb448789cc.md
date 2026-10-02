# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-10-02_equity_reit_v1@1.0_0adb448789cc`
**Ticker**: SGP.AX (Stockland Group)
**Market**: Australia
**Sector**: Diversified REIT / Residential Communities & Commercial
**As of**: 2026-10-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Stockland offers a headline distribution yield of approximately 6.3% at the current AUD 4.11 price, providing a meaningful absolute income return in the context of an RBA policy rate of 4.35% — though the yield spread is compressed versus historical norms. The diversified structure spanning residential communities, workplace & logistics, and town centres provides some earnings diversification, but residential development earnings remain the dominant driver and carry material cyclical risk under sustained elevated rates. Beta of 0.97 versus IASP.L (AUD/GBP currency basis caveat applies) indicates high co-movement with the APAC REIT universe and implies limited defensive characteristics. The OU Monte Carlo simulation yields a PGain of 64% over a 12-month horizon, reflecting wide dispersion (annualised sigma ~29%), and the base conviction is reduced one step to Conviction 2 (Low) on distribution coverage uncertainty given residential settlement risk.

## Quantitative Chain

- E(R): 0.0720
- Std dev: 0.1994
- P-gain: 0.6393
- CAPM alpha: 0.1217
- Beta: 0.9709
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - RBA holds rates at 4.35% through mid-2027, housing affordability deteriorates further reducing residential lot settlements by 20%+, DPU cut of 10-15% to protect balance sheet, cap rate expansion of 50bps across portfolio, price falls toward AUD 3.40-3.60 range. Bear case also captures a macro rate-shock scenario where global bond yields surge, compressing REIT multiples across the board.
- **base**: E(R)=0.0710
  - Central case as built in chain: DPU growth 1.0%, distribution yield ~6.3% at entry, modest negative multiple change of -0.4%. RBA holds or cuts once by year-end 2026, residential settlement volumes stabilise at current pace, workplace and logistics portfolio provides earnings stability.
- **bull**: E(R)=0.2200
  - RBA delivers 50-75bps of cuts in H1 2027 signalled in late 2026, residential communities re-rates on improved housing demand and first-home buyer support policy, logistics and workplace occupancy tightens, DPU growth accelerates to 3-4%, multiple expansion of 10-15% returns stock toward AUD 4.80-5.00.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.063 (Cat A) — Trailing DPU yield derived from Stockland FY2026 annual distribution of approximately 26 cents per security against closing price of AUD 4.11 on 2026-10-02. Results announced circa 19 August 2026 (high-volume spike day in price series confirming results release). Published distribution per security sourced from issuer announcement; price Category A from exchange data.
- `dpu_growth_3yr` = 0.01 (Cat C) — Forward DPU growth assumption of 1.0% p.a. reflecting: (i) modest organic rental escalation in workplace and logistics portfolio (~2-3% fixed escalations); (ii) offset by residential community settlement volumes under pressure in high-rate environment (RBA cash rate 4.35% as at September 2026 per BIS data); (iii) town centre retail stable but low-growth. Net growth conservatively estimated at 1% given 'FY2026 growth meets chart pressure' market commentary (Kalkine, 24 Sep 2026). Sensitivity tested in scenario analysis.
- `multiple_change` = -0.004 (Cat C) — Modest negative multiple change assumed (-0.4%) reflecting ongoing cap rate pressure from elevated RBA policy rate at 4.35%, de-rating observed in price series (stock declined from ~AUD 5.70 in Nov 2025 to AUD 4.11, approximately -28% over 12 months) and residential development re-rating risk. Conservative assumption that cap rate headwinds partially but not fully persist over next 12 months.
- `rba_policy_rate` = 0.0435 (Cat A) — RBA cash rate target at 4.35% as at observation date 2026-09-24 (age 8 days), sourced from BIS WS_CBPOL series for Australia. Key input for assessing yield spread and gearing cost environment.
- `leverage_gearing` = ~26pct_estimated (Cat B) — Stockland's look-through gearing estimated at approximately 26% based on historical disclosures in FY2024/FY2025 annual reports (range 24-28%). Filing body capture for ASX filings in the stored pipeline returned mismatched document bodies for SGP.AX — bodies were for unrelated ASX entities. Estimate derived from public disclosures and confirmed to be well within the Australian REIT 40% gearing convention.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise. High beta of 0.97 may overstate true property-market sensitivity given AUD/GBP volatility embedded in the 252-day window.

## Key Risks
- Sustained elevated RBA cash rate (4.35%) compresses residential lot demand and delays settlements, impairing DPU coverage below 1.0x AFFO
- Cap rate expansion in workplace/logistics assets as investment market adjusts to higher long-run interest rate environment, eroding NTA and triggering potential covenant scrutiny
- High annualised volatility of ~29% (252-day realised) reflects significant market uncertainty and creates wide return dispersion around the base case
- Filing body capture pipeline returned mismatched documents for SGP.AX filings — specific FY2026 gearing, WALE, and coverage data could not be independently verified from stored filings; estimates rely on historical public disclosures
- Residential communities earnings concentration (estimated >50% of group FFO) exposes the trust to housing cycle downturns, government policy changes to negative gearing or capital gains concessions, and construction cost inflation

## Invalidation Condition
Exit or reduce position if Stockland announces FY2027 DPU guidance implying a distribution cut of more than 10% versus FY2026 actuals, or if reported look-through gearing rises above 35% (approaching the 40% Australian REIT convention ceiling), or if RBA raises the cash rate above 5.00%, or if residential community lot settlement volumes decline more than 25% for two consecutive half-year periods relative to the prior corresponding period, each of which would materially impair the distribution yield and NAV assumptions underpinning this memo.
