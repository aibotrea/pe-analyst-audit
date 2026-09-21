# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-09-21_equity_reit_v1@1.0_0997e4ceee6d`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-09-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is the pre-eminent listed industrial and logistics property manager in the Asia-Pacific, with an increasingly significant data-centre development pipeline that commands a structural earnings-per-security growth premium over traditional A-REITs. FY2026 operating profit of ~AUD 1.2B and confirmed Q3 2026 guidance reinforce a 12% forward EPS growth trajectory, supported by a conservative balance sheet (look-through gearing ~13-15%) well inside Australian convention limits. The distribution yield of ~1.2% is low relative to peers, but the total-return case is driven by capital appreciation from development completions and fund management AUM growth rather than income distribution. The OU Monte Carlo (PGain 72%, sim return 11.1%) supports a moderate conviction rating, with volatility (annualised 28%) elevated for the REIT sector and reflecting GMG's hybrid property-developer / fund-manager character — a -1 gate override applied for hyperscaler tenant concentration risk and benchmark signal unreliability.

## Quantitative Chain

- E(R): 0.1120
- Std dev: 0.1908
- P-gain: 0.7199
- CAPM alpha: 0.1371
- Beta: 0.7232
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Operating EPS growth slows to 5% (hyperscaler capex cuts and logistics demand softening); cap rate expansion of 50bps compresses NTA by ~15%; multiple contraction -8% as rate-sensitive premium unwinds; distribution yield offers minimal support at 1.2%. Bear case also encompasses a rate-shock scenario where RBA holds rates above 4.5% into 2027, further pressuring the NTA premium and development feasibility.
- **base**: E(R)=0.1110
  - Central case as modelled: distribution yield 1.17%, operating EPS growth 12%, multiple contraction -2%. Occupancy stable across logistics portfolio (~97%), data-centre WIP progresses on schedule, RBA begins moderate easing cycle in H1 2027. OU Monte Carlo sim return 11.1%, PGain 72%.
- **bull**: E(R)=0.2800
  - Operating EPS growth accelerates to 16% driven by data-centre completions ahead of schedule and AUM expansion exceeding AUD 100B; multiple re-rates +5% as market ascribes higher fund-management earnings multiple; RBA cuts 75bps by mid-2027 reducing cap rate pressure; AUD strengthens modestly reducing import cost inflation on construction.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0117 (Cat A) — Trailing FY2026 distribution of approximately AUD 0.30 per stapled security (H1 + H2 payments; distribution dispatch announced 2026-08-26 on ASX by GMG). Divided by closing price AUD 25.65 on 2026-09-21. Low payout ratio is structural for GMG given significant retained earnings deployed into development pipeline.
- `operating_eps_growth_3yr` = 0.12 (Cat C) — Forward operating EPS growth assumption of 12% p.a. (3-year tapering CAGR). Grounded in: (1) GMG Q3 2026 earnings call confirming strong data-centre and logistics pipeline growth trajectory; (2) FY2026 $1.2B operating profit reported (Australian Property Markets News, Feb 2026); (3) market consensus of ~15% FY2026 EPS growth, fading to ~10-12% over the following 2 years as development completions moderate. Sensitivity: bull case uses 16%, bear case uses 5%.
- `multiple_change` = -0.02 (Cat C) — Assumed -2% multiple contraction over 12 months. GMG trades at a material premium to NTA (estimated 40-60% premium) reflecting fund management earnings and development margin. In a higher-for-longer rate environment with AUD 10Y yields elevated, some premium compression is probable. Sensitivity: bull case flat/+2%, bear case -8%.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. The IASP.L 5-year annualised return of -5.0% is heavily influenced by AUD/GBP FX movements over the period and should not be read as a pure property-market signal.
- `expected_market_return` = -0.05 (Cat B) — Trailing 5-year annualised log return of IASP.L benchmark (1,304 observations, ~5.17 years as of 2026-09-21). Negative return (-5.0%) reflects both APAC REIT property price weakness and AUD/GBP FX headwinds. As a Category B input with material currency-basis noise, the CAPM-derived required return (-2.5%) is directionally unreliable and treated as supporting context only.
- `gearing_assumption` = 0.135 (Cat B) — GMG look-through gearing estimated at approximately 13-15% of total assets (balance-sheet gearing) based on publicly disclosed FY2026 results. Well within Australian REIT convention threshold of <40%. Per ASX distribution announcement (GMG.AX, 2026-08-26) and known capital structure. Exact figure pending full annual report release.

## Key Risks
- Hyperscaler demand slowdown or capital expenditure cuts by major cloud tenants (Microsoft, Amazon, Google) would directly impair GMG's data-centre development pipeline and compress NAV realisation timelines.
- Higher-for-longer AUD interest rates compressing cap rates and widening the NTA discount, particularly as GMG's elevated price-to-NTA premium (~40-60%) has limited margin of safety if sentiment shifts.
- AUD/GBP and AUD/USD FX movements introduce material noise into beta and benchmark return signals; CAPM-derived required return (-2.5%) is unreliable given IASP.L's negative 5-year return, reducing confidence in the alpha estimate.
- Development execution risk: GMG carries a large work-in-progress portfolio; construction cost inflation, permitting delays, or post-completion leasing shortfalls could impair development margins and operating EPS.
- Backtest/calibration limitation: Phase 2 calibration is a directional signal only; vintage discipline not yet formalised (Phase 5). Conviction score should be treated as indicative.

## Invalidation Condition
Exit GMG.AX if: (1) operating EPS growth guidance is formally revised below 5% for two consecutive half-year reporting periods, indicating structural deceleration of the development pipeline; or (2) look-through gearing rises above 30% of total assets, signalling a material balance-sheet risk shift; or (3) a named major hyperscaler customer (>10% of WIP by value) formally cancels or indefinitely defers a committed data-centre lease pre-construction completion; or (4) the closing price falls more than 25% below the NTA per security as disclosed in the most recent audited accounts, indicating market pricing of fundamental impairment.
