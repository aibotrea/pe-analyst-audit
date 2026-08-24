# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-24_equity_reit_v1@1.0_4f622aa25882`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT is at a structural inflection point, pivoting its portfolio away from North American data centres (US$315.9M disposal announced 12 August 2026) toward Singapore and Japan in pursuit of APAC demand tailwinds. The recurring income yield of ~3.54% — stripped of the non-recurring capital distribution component representing 49% of 1H26 DPU — sits marginally below the current 3.72% T-bill rate, making the income case contingent on successful APAC deployment delivering DPU growth. Digital Realty's Tier-1 sponsor credentials and the ongoing unit buyback programme (cancelling units at market prices, mandate up to 129.6M units) provide structural support, and a CAPM alpha of +5.7% versus IASP.L is encouraging on a risk-adjusted basis. However, execution risk on new-market entry, unconfirmed post-transaction gearing, and distribution sustainability concerns limit conviction to low, warranting a reduced position size until the APAC asset operational track record is established.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1619
- P-gain: 0.6543
- CAPM alpha: 0.0565
- Beta: 0.3560
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - APAC acquisitions fail to achieve target yields; occupancy at newly acquired Singapore and Japan assets falls below 85%; recurring DPU resets downward as capital distribution is exhausted and income coverage deteriorates; gearing rises above 45% regulatory threshold triggering forced asset sales; data centre cap rate expansion of 50bps on AI demand disappointment or rate shock.
- **base**: E(R)=0.0650
  - Central case: income yield 3.54% + DPU growth 2.0% + re-rating 1.0% = 6.5%. APAC repositioning proceeds on plan, occupancy at new assets stabilises above 90%, gearing remains within 45% limit post-disposal, unit buyback continues to support per-unit metrics.
- **bull**: E(R)=0.2200
  - Full re-rating as APAC data centre demand accelerates on AI infrastructure buildout; Singapore and Japan assets achieve yield-on-cost above 7%; total DPU recovers to USD 0.035+ annualised; unit buyback meaningfully reduces float; Digital Realty sponsor injects additional pipeline assets at accretive terms; discount to NAV closes substantially.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0354 (Cat A) — Recurring income DPU annualised: 0.92 US cents per unit (1H26 income component) × 2 = 1.84 US cents, divided by closing price USD 0.52. Source: DCRU.SI 2026-07-29 CACT filing. Total DPU 1.80c per half includes 0.88c capital distribution (return of capital from US asset disposals); only recurring income component used for sustainable yield.
- `capital_distribution_note` = 0.0338 (Cat A) — Capital distribution component: 0.88 US cents per unit for 1H26 = 1.76c annualised / USD 0.52 = 3.4% additional return. This reflects proceeds from the US$315.9M North American data centre disposal announced 12 August 2026 (trading halt 11 Aug, lifted 12 Aug). Excluded from sustainable income yield but noted as a one-time capital return. Source: DCRU.SI 2026-07-29 CACT filing.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption: 2.0% p.a. APAC repositioning — proceeds from US$315.9M North American disposal redeployed into Singapore (debut) and Japan expansion (announced 12 Aug 2026). APAC data centres expected to generate higher accretive yields in current demand environment. Sensitivity: bear 0%, bull 4%.
- `multiple_change` = 0.01 (Cat C) — Modest positive re-rating: +1.0% from reduced US geopolitical risk premium and APAC portfolio alignment with regional investor preferences. High uncertainty post-restructuring; sensitivity tested in scenario analysis.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU trades and distributes in USD on SGX). Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Distribution sustainability: 49% of 1H26 DPU (0.88c of 1.80c) is capital return from US disposals, not recurring income; bare income yield of ~3.5% is below the T-bill rate without growth realisation
- APAC acquisition execution: Singapore debut and Japan expansion involve simultaneous new-market entry with uncertain lease-up timelines, yield-on-cost achievement, and regulatory approvals
- Leverage and capital structure uncertainty: post-disposal gearing and net debt position not confirmed from available truncated filings; equity issuance to fund APAC acquisitions would be dilutive if priced below NAV
- Sponsor and tenant concentration: Digital Realty-affiliated entities historically represent significant lease concentration; any deterioration in Digital Realty's credit or strategy cascades to DCRU occupancy
- USD currency basis: DCRU distributes in USD; APAC asset acquisitions introduce SGD and JPY asset valuation mismatches, while Singapore unitholder base bears USD/SGD FX risk on distributions

## Invalidation Condition
Exit position if recurring income DPU (excluding capital distributions) falls below 0.80 US cents per unit per half-year for two consecutive reporting periods, or if aggregate leverage exceeds 45% of deposited property value, or if Digital Realty formally reduces its sponsorship commitment or pipeline to DCRU, or if newly acquired Singapore or Japan assets report occupancy below 85% in their first full operational quarter post-acquisition completion.
