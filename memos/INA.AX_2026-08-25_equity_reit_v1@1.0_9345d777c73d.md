# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-08-25_equity_reit_v1@1.0_9345d777c73d`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Lifestyle/Land-Lease Communities
**As of**: 2026-08-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Ingenia Communities offers differentiated exposure to Australia's structurally undersupplied land-lease/lifestyle community sector, underpinned by ageing demographic tailwinds and a growing portfolio of ~130+ communities. The FY2026 results released on 2026-08-25 carried the headline 'Guidance Exceeded', signalling operational resilience despite property valuation headwinds flagged in recent market commentary. At AUD 4.26, the estimated distribution yield of ~3.4% is modest relative to the T-bill rate (3.72%), but the total return thesis depends on DPU growth (5% p.a. forward estimate) from new home deliveries and organic site rent escalation rather than yield alone. Beta of 0.68 vs IASP.L (currency-basis caveat applies) and annualised volatility of 24.7% reflect a moderately leveraged growth REIT; the OU Monte Carlo PGain of 67.9% at a 12-month horizon supports a moderate conviction rating of 3.

## Quantitative Chain

- E(R): 0.0790
- Std dev: 0.1681
- P-gain: 0.6790
- CAPM alpha: 0.0973
- Beta: 0.6808
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Property valuations decline 5-8% driven by cap rate expansion of 50bps (RBA holds rates higher for longer or lifts further); home sales volumes fall 20% as housing affordability deteriorates and discretionary retirement spending contracts; DPU growth stalls at 0%; gearing rises toward 40% constraining buyback/development capacity; multiple compression adds an additional -5% to total return drag. Stagflation scenario (persistent inflation + slowing economy) worsens new-community absorption rates.
- **base**: E(R)=0.0790
  - Central case as built in quantitative chain: DPU yield 3.4%, DPU growth 5% p.a., modest cap rate expansion -0.5% multiple drag, gearing stable at ~37%, occupancy broadly stable, RBA on hold or mildly easing.
- **bull**: E(R)=0.2000
  - RBA cuts cash rate 75bps over 12 months driving cap rate compression and NAV uplift; home sales volumes accelerate as retirement demand recovers post rate-cut cycle; DPU growth of 8-10% from new community completions and above-CPI rent escalations; market re-rates land-lease sector toward 5% cap rate (from ~5.5% currently), delivering ~10% NAV uplift on top of distribution income.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.034 (Cat B) — Estimated FY2026 DPU of ~14.5 cents per security (derived from prior FY2025 actuals of ~14.1 cpu plus guidance-exceeded signal from INA.AX ASX price-sensitive release dated 2026-08-25 'Continued Delivery Against Strategy - Guidance Exceeded') divided by closing price AUD 4.26. Category B as DPU is an analyst estimate pending full FY2026 report detail; filing body unavailable for INA.AX (ASX body capture pending).
- `dpu_growth_3yr` = 0.05 (Cat C) — Forward DPU growth of 5% p.a. reflects structural tailwind from ageing demographics driving land-lease community demand, organic rental escalation (typically CPI-linked), and new home deliveries from development pipeline. Sensitivity tested in scenario analysis. Source: analyst estimate; no issuer guidance figure confirmed from filing body.
- `multiple_change` = -0.005 (Cat C) — Modest cap rate expansion assumption of ~15bps over 12 months reflecting news signal ('Ingenia Communities Retreats as Market Focus Turns to Property Valuations and Growth', Kalkine, 24 Jul 2026) and RBA rate environment. Translates to approximately -0.5% multiple drag on total return. Category C; sensitivity tested in bear scenario.
- `gearing_ratio` = 0.37 (Cat B) — Estimated balance sheet gearing of ~37% based on FY2025 published accounts and typical Ingenia Communities LVR range of 35-38%. Within Australian REIT convention of <40%. Filing body for 2026 annual results was unavailable (body_unavailable per ASX pipeline); figure is a carry-forward estimate pending FY2026 full accounts.
- `distribution_coverage` = 1.05 (Cat B) — Estimated AFFO coverage of ~1.05x based on Ingenia's conservative payout ratio (distributes ~40-45% of statutory earnings; significant portion of cash flow retained for development capex). Land-lease model generates recurring site rental income plus lumpy home-sale profit. Category B estimate; FY2026 filing body unavailable.
- `rba_cash_rate` = 0.04 (Cat C) — RBA cash rate assumed at approximately 4.0% as of 2026-08-25. RBATCTR FRED series not available; live APAC rates call returned empty. Estimate consistent with RBA policy trajectory documented in public releases. Category C proxy rate used for local funding cost context only; US T-bill (3.72%) used as Rf in CAPM.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP.L 5-year annualised return of -4.43% also reflects GBP/AUD and GBP/USD currency movements over the observation window.

## Key Risks
- RBA rate persistence or further hikes compressing the yield spread and triggering property cap rate expansion, which would reduce NTA and pressure the unit price.
- New home sales volumes are cyclically sensitive; a housing market slowdown in southeast Australia could impair development earnings, which underpin the DPU growth assumption.
- Property valuation headwinds highlighted in recent market commentary; any downward revaluation in the FY2026 accounts (full text body unavailable at analysis date) could signal a weaker NTA than assumed.
- Gearing estimated at ~37%; if property values fall and gearing breaches 40%, this could constrain development pipeline and trigger covenant scrutiny.
- Filing body for FY2026 annual results was unavailable at time of analysis (ASX body capture pending); key metrics including NTA, gearing, DPU and AFFO coverage could not be directly sourced from the filing and are carried as estimates.

## Invalidation Condition
Exit if FY2026 reported gearing exceeds 40% of total assets on a look-through basis, or if DPU for FY2026 is confirmed more than 10% below the 14.5 cpu estimate (implying AFFO coverage below 0.95x), or if Ingenia announces a pause or material reduction in its development pipeline commitments for two consecutive half-year periods, or if NTA per security declines by more than 15% from the FY2025 reported figure.
