# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-09-03_equity_reit_v1@1.0_6feedea239ae`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Commercial Office/Industrial
**As of**: 2026-09-03
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Growthpoint Properties Australia offers a high income yield of approximately 9.0% at the current AUD 2.05 price, underpinned by FY26 DPU of 18.4c delivered in line with guidance and record portfolio occupancy of 96% driven by record-pace office leasing. The OU Monte Carlo simulation returns a 12-month expected return of 10.9% with a P(gain) of 79.7%, reflecting a favourable risk-reward skew even accounting for the 19.4% historical volatility. The primary constraint is gearing at approximately 41%, which modestly exceeds the Australian REIT convention threshold of 40% and warrants a one-step conviction reduction. Alpha of 0.12 is mechanically inflated by the deeply negative IASP.L 5-year benchmark return (a currency-basis artefact) and should not be relied upon as a standalone signal.

## Quantitative Chain

- E(R): 0.1100
- Std dev: 0.1319
- P-gain: 0.7965
- CAPM alpha: 0.1204
- Beta: 0.5728
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Cap rates expand 50bps as RBA holds rates higher for longer, compressing NTA by ~8-10%; DPU cut to 16.5c as tenant vacancies emerge and occupancy falls from 96% back toward 90%; gearing breaches 45% covenant threshold triggering equity raising at discount; AUD/GBP FX headwind amplifies IASP.L beta-driven drawdown. Stagflation scenario (elevated CPI + weak growth) would accelerate office demand erosion and impair reversion rents.
- **base**: E(R)=0.1100
  - Central case as built in quantitative chain: FY27 DPU growth 1.5% to ~18.7c, occupancy stable at 96%, gearing gradually reduced toward 39% via asset recycling, cap rates flat, AUD broadly stable versus USD/GBP.
- **bull**: E(R)=0.2400
  - RBA rate cuts materialise in H1 FY27 (75bps), compressing cap rates by 25-40bps; price-to-NTA discount closes as sentiment toward commercial office improves; DPU growth accelerates to 3%+ on record leasing conversions and rent reversion uplift; gearing falls below 38% on asset disposals at or above book; yield-seeking inflows from superannuation funds compress GOZ's risk premium.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0898 (Cat A) — FY26 DPU of 18.4 cents (matched guidance per Motley Fool Australia, 22 Jun 2026) divided by closing price of AUD 2.05 on 2026-09-03. Observed published distribution and market price.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a.: modest organic growth reflecting record 96% portfolio occupancy (Kalkine/Investing.com, Aug 2026) offset by lingering Australian commercial office structural headwinds. Sensitivity tested in scenario analysis: bear -1.0%, bull +3.0%.
- `multiple_change` = 0.005 (Cat C) — Mild cap-rate compression / price-to-NTA mean reversion contributing +0.5% to total return. GOZ has traded at a discount to NTA; record leasing and occupancy improvement at 96% support a partial re-rating. Assumption is conservative relative to sector uplift. Sensitivity: bear -2.0% cap-rate expansion, bull +2.0% re-rating.
- `gearing_ratio` = 0.41 (Cat B) — Gearing of approximately 41% cited in Kalkine media article ('Can an 8% Yield Survive Office Headwinds and 41% Gearing?', 15 Jun 2026). Slightly exceeds the Australian REIT convention threshold of <40%; confirmed as Category B derived estimate from third-party reporting. Used in leverage gate assessment.
- `portfolio_occupancy` = 0.96 (Cat B) — FY26 portfolio occupancy of 96% sourced from 'Growthpoint FY26 slides: occupancy hits 96% on record leasing' (Investing.com, 16 Aug 2026) and corroborated by Kalkine (3 Aug 2026, 1 Sep 2026). Classified Category B as sourced from third-party synthesis of issuer slide content.
- `affo_coverage` = unavailable (Cat B) — Annual Report body (GOZ FY26 Appendix 4E and Annual Report, filing_date 2026-08-16) was captured but pipeline returned mismatched document content from an unrelated ASX issuer. AFFO/DPU coverage ratio could not be confirmed from stored filings. Disclosed as data gap; distribution_coverage gate assessed as 'info'. GOZ historically distributes at 100% of FFO — modest downside risk if income softens.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Gearing at ~41% slightly exceeds the Australian REIT <40% convention threshold; further cap-rate-driven NTA compression could push reported gearing toward covenant limits, potentially requiring a dilutive equity raising.
- Structural demand risk in Australian commercial office: hybrid work patterns remain entrenched; any demand reversal would quickly erode the record 96% occupancy improvement and compress reversion rents.
- RBA higher-for-longer scenario widens the spread between GOZ's cost of debt and distribution yield, reducing FFO headroom and DPU coverage — particularly as fixed-rate hedges roll off.
- AFFO coverage ratio could not be confirmed from stored filings due to pipeline document mismatch; if distributions exceed AFFO (i.e., coverage below 1.0x), the yield is partially a return of capital.
- IASP.L benchmark is GBP-denominated; computed beta (0.573) and CAPM alpha absorb AUD/GBP currency noise, reducing precision of the CAPM signal as a standalone conviction input.

## Invalidation Condition
Exit or reduce position if portfolio occupancy falls below 92% for two consecutive half-year reporting periods, or if GOZ announces a distribution cut below 17.0 cents per unit on an annualised basis, or if reported gearing rises above 45% (whether from asset devaluations or debt drawdowns), or if the sponsor Growthpoint Properties South Africa materially reduces its unitholding or withdraws management alignment commitments.
