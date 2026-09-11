# Specialist Memo — CHC.AX

**Memo ID**: `CHC.AX_2026-09-11_equity_reit_v1@1.0_743d7c34889b`
**Ticker**: CHC.AX (Charter Hall Group)
**Market**: Australia
**Sector**: Property Funds Management / Diversified A-REIT
**As of**: 2026-09-11
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Charter Hall Group is a diversified Australian property funds manager with a multi-decade track record of AUM growth across industrial, office, retail and social infrastructure mandates. FY26 earnings jumped 27% on record equity inflows and transactions, yet the stock declined approximately 30% from its December 2025 peak to AUD 18.12, suggesting a potential valuation opportunity. However, high historical volatility of 28.3%, lumpy performance-fee-dependent income, and a senior leadership reshuffle disclosed alongside FY26 results introduce meaningful uncertainty. The OU Monte Carlo simulation yields a PGain of 64.6% at a 12-month horizon — consistent with a Low conviction score of 2/5 after applying a one-step downward override for management alignment risk.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1921
- P-gain: 0.6463
- CAPM alpha: 0.1137
- Beta: 0.8944
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - AUM contracts as institutional capital redemptions accelerate amid office sector distress and persistent RBA rate elevation; performance fees collapse to near zero reducing EPS by 15-20%; distribution cut 20%; further multiple contraction of -15% as markets reprice the funds management model. Leadership reshuffle causes key client departures. CHC share price targets AUD 13-14.
- **base**: E(R)=0.0730
  - Central case as constructed in the quantitative chain: normalised DPS growth 7%, distribution yield ~2.3%, -2% multiple contraction. AUM grows modestly from FY26 base; performance fees normalise below record FY26 levels. Leadership transition managed without material client loss. CHC share price targets AUD 19-20 over 12 months.
- **bull**: E(R)=0.2500
  - AUM accelerates to new highs as private capital allocations to Australian real assets increase; performance fees sustain FY26 record levels or exceed them; fresh leadership provides positive strategic optionality. RBA delivers 50bps of rate cuts, compressing cap rates and boosting managed portfolio valuations. DPS growth 12%+ drives re-rating toward long-run P/E mean, targeting AUD 22-24 per security.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.023 (Cat A) — Trailing distribution yield estimated at approximately 2.3%, based on ~42 cents per security annualised distribution against the observed closing price of AUD 18.12 on 2026-09-11. CHC FY26 results (reported August 2026) showed 27% earnings growth; DPS estimate sourced from Kalkine news context (21 Aug 2026, 31 Aug 2026). Security price is Category A (observed); DPS estimate is Category B by derivation, blended and disclosed at A for the yield line.
- `dpu_growth_3yr` = 0.07 (Cat C) — Forward earnings/DPS growth assumption of 7% per annum normalised over a 3-year horizon. CHC reported a 27% FY26 earnings jump driven by record equity inflows and AUM growth (Kalkine, 21 Aug 2026: 'Charter Hall Group Lifts Earnings Outlook After Record Equity Inflows'). A 7% normalised rate accounts for mean reversion in lumpy performance fees while capturing secular AUM compounding. Bull case 12%, bear case 0%.
- `multiple_change` = -0.02 (Cat C) — Assumed -2% P/E multiple contraction over the 12-month horizon. CHC declined approximately 30% from its December 2025 peak of ~AUD 25.66 to AUD 18.12 at the analysis date, reflecting negative market sentiment around FY26 results, office sector headwinds, and the leadership reshuffle. A modest further compression assumption is applied; sensitivity: bear -15%, bull +10% multiple expansion.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency noise. AUD/GBP basis volatility of approximately 8-10% annualised is material relative to the computed beta of 0.894, and may cause the beta to overstate or understate true property-market co-movement.
- `fee_income_concentration` = disclosed (Cat B) — CHC derives a substantial proportion of earnings from performance fees and management fees tied to AUM across Charter Hall-managed A-REITs including CLWOF, CQR, CLW, CPOF and others. Performance fees are lumpy and capital-markets-correlated. This structurally increases earnings volatility relative to a direct-property REIT. Sourced from public business description and Kalkine news analysis, August-September 2026.
- `leadership_transition_risk` = disclosed (Cat B) — Senior leadership reshuffle disclosed in connection with FY26 results (Kalkine, 31 Aug 2026: 'FY26 Earnings Jump 27% Amid a Senior Leadership Reshuffle'). Management continuity risk is a qualitative factor that informed the -1 gate override applied to the management_alignment qualitative gate.

## Key Risks
- Performance fee income is highly lumpy; normalisation of capital markets activity post-FY26 could cause sharp EPS and DPS downside, invalidating the 7% forward growth assumption
- Office sector asset value deterioration within Charter Hall-managed portfolios could trigger AUM redemptions and fee compression, amplifying CHC's already elevated 28.3% historical volatility
- Senior leadership reshuffle (disclosed August 2026) risks disrupting key institutional investor relationships and AUM fundraising pipelines, weakening the competitive moat
- RBA higher-for-longer rate environment compresses Australian property valuations, increasing withdrawal risk from wholesale capital partners across CHC-managed vehicles
- CAPM alpha of 11.4% is significantly inflated by the weak IASP.L 5-year benchmark return of -5.0% and AUD/GBP currency basis noise; true risk-adjusted alpha is likely materially lower than reported

## Invalidation Condition
Exit the position if Charter Hall reports two consecutive half-year periods of aggregate AUM decline exceeding 5% of opening AUM, or if performance fee income falls to zero for a full financial year, or if a further C-suite departure (CEO or CIO level) occurs within 12 months of the August 2026 leadership reshuffle, or if the distribution per security is cut by more than 15% relative to FY26 actuals without a corresponding share buyback program offsetting shareholder returns.
