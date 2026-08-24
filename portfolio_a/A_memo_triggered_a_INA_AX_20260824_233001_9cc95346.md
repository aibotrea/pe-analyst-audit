# Track A Decision — INA.AX

**Decision ID**: `A_memo_triggered_a_INA_AX_20260824_233001_9cc95346`
**Flow context**: memo_triggered_a
**Decided at**: 2026-08-24T23:30:01.838349+00:00
**Decided by**: gp
**Source memo**: [`INA.AX_2026-08-24_equity_reit_v1@1.0_4dd893bb6b24`](../memos/INA.AX_2026-08-24_equity_reit_v1@1.0_4dd893bb6b24.md)
**GP cycle**: `A_cycle_2026-08-24T23:30:01.838349+00:00_948af57f`

## Action

- **Action**: `reject`
- Conviction-implied target: 3.00%

## Reasoning

**Reason class**: `reject_thesis_disagreement`

INA.AX cannot be added to the portfolio in the current state of information. The portfolio already holds INA.AX at 1.01% weight from position 95 (entered 2026-08-02), which is itself already underwater at -1.31% PnL. The memo's own conviction-2 assessment is driven primarily by a completely unresolved price-sensitive Trading Halt entered 2026-08-23 — one day before the memo date — whose nature is entirely unknown due to ASX body capture failure. A management_alignment gate FAIL with -1 override is applied. The PGain of 63.5% is the lowest in this batch and the bear case (-12%) is steep. Adding to a position when a material corporate event is pending and unresolved, with management alignment flagged as failed, directly contradicts prudent investment process — the thesis cannot be adequately underwritten when the most material near-term catalyst is completely opaque. The existing 1% position is an adequate holding; no incremental capital should be deployed until the trading halt resolves and its implications are assessed.

## Post-Decision Exposures

- Total invested: 89.56%
- Country: `{"Singapore": 31.63, "Japan": 33.1, "Australia": 24.84}`
- Sector: `{"Healthcare": 5.04, "Office": 13.94, "Diversified": 23.38, "Industrial/Logistics": 17.85, "Retail": 12.27, "Residential": 4.19, "Data Centre": 12.89}`
