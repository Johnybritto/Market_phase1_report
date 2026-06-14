# Stock Watchlist Workflow Rules — Phase 1, Phase 2 and Phase 3

Last updated: 14 June 2026

This file is the operating rulebook for the stock watchlist workflow.

Repository: `Johnybritto/Market_phase1_report`

---

## 0) Core Workflow

The workflow has three phases:

1. **Phase 1** — Daily watchlist scanner and actionable shortlist.
2. **Phase 2** — User selection/input step.
3. **Phase 3** — Detailed deep-dive report for selected stock(s).

The daily job should focus on useful stock information first. GitHub saving is secondary housekeeping and must never replace the actual report.

---

## 1) Phase 1 Rules — Daily Watchlist Report

### 1.1 Purpose

Phase 1 is the daily after-market watchlist scanner. It should internally scan the full watchlist universe, but display only a clean actionable shortlist.

The goal is not to show every stock. The goal is to help decide what to focus on today.

---

### 1.2 Watchlist Master Source

Use the latest completed watchlist master in the File Library as the primary universe.

Preferred master file:

`watchlist_master_52w_retry_completed_2026-05-30.xlsx`

This file is treated as the source of truth for:

- Stock names
- NSE symbols
- BSE codes
- Listing status
- SME / unlisted / theme status
- Sector / theme
- 52-week high
- 52-week low
- 52W source
- 52W last verified date

Use the older `watchlist.xlsx` only as fallback.

The full master universe must be covered internally, not only recently discussed stocks.

---

### 1.3 Current Price Rules

For current price, use fresh EOD/latest close only. Do not use stored workbook current prices for scoring.

Price source priority:

1. NSE official EOD / latest exchange close / CM-UDiFF / bhavcopy
2. BSE official EOD / latest exchange close / bhavcopy
3. Reliable free EOD/latest-close fallback sources such as Samco, Screener, Groww, Trendlyne, Moneycontrol, Yahoo Finance, Google Finance or other reputable market pages
4. Market pages only for cross-checking or priority rows

The Current Price column must include the price basis inside the same cell.

Allowed examples:

- `₹739 NSE EOD`
- `₹303 fallback close`
- `₹931 BSE EOD`
- `Price mismatch / No score`
- `Corporate-action mismatch / No score`

Do not show a bare price without source basis.

---

### 1.4 52-Week High/Low Rules

Use 52-week high/low from the completed master sheet.

Do not fetch 52W high/low daily unless:

- Current price breaks a new 52W high/low, or
- A periodic refresh is requested, or
- A corporate action creates an adjustment mismatch.

If 52W data is missing or mismatched, do not guess. Use `Data Check / No score`.

---

### 1.5 Phase 1 Output Format

Start exactly with:

`## Phase 1 Watchlist Report — DD Month YYYY`

Include only these three sections:

1. `Market Backdrop`
2. `Watchlist Decision Table`
3. `Count Summary`

Do not create separate Phase 1A and Phase 1B tables.

---

### 1.6 Market Backdrop Rules

Section 1 must contain exactly 3 concise bullets.

The backdrop should cover:

- Broad market tone
- Key risk/trigger of the day
- Practical Phase 1 stance

Do not overload the report with excessive macro commentary.

---

### 1.7 Section 2 Table Columns

The Watchlist Decision Table must use only these columns:

| Stock | Deep Dive? (Yes/Maybe/No) | Current Price | 52W High/Low | Buy Safety Score | 52W High Breakout Score | Outcome Bias | Action |
|---|---|---|---|---|---|---|---|

No Category column.
No buy-range columns in Phase 1.
No long neutral watchlist dump.

---

### 1.8 Section 2 Selection Rules

Section 2 should be capped to around 15–25 useful rows.

Include only:

- Deep Dive = Yes names
- Accumulate candidates
- Watch for Dip candidates
- Breakout Watch candidates
- Tactical Event Plays
- Stocks near 52W low/support with valuation comfort
- Important Avoid Fresh Buy warnings
- Data Check / No score rows that must be flagged
- User-holding/concentration warnings

Do not include every neutral Track Only stock.

Track Only should not enter Section 2 unless one of these is true:

- Deep Dive? = Yes
- Important warning
- Price/mapping/data issue
- Meaningful user-holding/concentration warning

Neutral names should be summarized only in Section 3.

---

### 1.9 Fixed Action Taxonomy

Use only these action buckets/phrases:

1. `Accumulate`
2. `Watch for Dip`
3. `Breakout Watch — no chase / retest only`
4. `Tactical Event Play`
5. `Deep Dive Needed`
6. `Avoid Fresh Buy`
7. `Data Check / No score`
8. `Theme Watch`

Do not use inconsistent labels such as:

- Buy Small
- Track closely
- Hold / Track
- Maybe accumulate
- Wait and watch
- Generic Track Only in Section 2

Nuance can be explained after the fixed action phrase.

Example:

`Accumulate — valuation comfortable and price near lower 52W band; stagger only.`

---

### 1.10 Score Rules

Use strict 0–100 scale only.

- Buy Safety Score must be an integer from 0 to 100.
- 52W High Breakout Score must be an integer from 0 to 100.
- Never use `/10` scores such as `7/10` or `8.5/10`.
- Never use decimal score formats such as `7.5` or `8.0`.
- If an old `/10` score is considered internally, convert it before publishing. Example: `7/10` becomes `70`.
- If price, mapping or corporate-action data is doubtful, use exactly `No score` in both score columns.

---

### 1.11 Score-to-Action Mapping

Default action mapping:

| Condition | Default Action |
|---|---|
| Buy Safety Score >= 75 and valuation/fundamentals comfortable | Accumulate |
| Buy Safety Score 60–74 | Watch for Dip |
| 52W High Breakout Score >= 70 and Buy Safety Score < 60 | Breakout Watch — no chase / retest only |
| Meaningful corporate event with risk | Tactical Event Play |
| Good business but deeper confirmation needed | Deep Dive Needed |
| Price mismatch, corporate-action mismatch, stale price, symbol issue or mapping issue | Data Check / No score |
| Weak earnings, high debt, high pledge, governance concern, liquidity risk or speculative turnaround | Avoid Fresh Buy |
| Unlisted / upcoming IPO / theme row | Theme Watch |

Expensive stocks can have high breakout probability, but the action must not become Buy Now. Use retest/no-chase language.

---

### 1.12 Mandatory Action Trigger

Every Section 2 Action must include a short trigger or reason.

Examples of valid triggers:

- Price near 52W low/support
- Valuation comfort
- Earnings/news trigger
- Event risk
- Retest/no-chase requirement
- Data mismatch
- Concentration warning
- Avoid reason such as debt, pledge, weak earnings or liquidity risk

Do not publish vague actions like only `Accumulate` or only `Watch for Dip`.

---

### 1.13 Breakout Watch Discipline

Every Breakout Watch row must mention either:

- A retest level,
- A support/retest zone, or
- The phrase `no chase`.

If a precise level cannot be validated, use:

`Breakout Watch — no chase / retest only; wait for support confirmation.`

---

### 1.14 Corporate-Action and Data-Fix Discipline

Do not classify data or corporate-action problems as Avoid Fresh Buy unless the business itself has a real risk.

Examples that should go to `Data Check / No score`:

- Split/bonus adjustment mismatch
- Stale current price
- 52W high/low mismatch
- BSE/NSE source conflict
- Symbol conflict
- Mapping issue

Scores must be `No score` for these rows.

---

### 1.15 Repeated-Stock / Freshness Discipline

Avoid letting the same 10–12 stocks dominate every visible Phase 1 report.

Do not force fresh names daily, but on a rolling weekly basis at least 3–5 fresh qualifying names should be considered for Section 2 if they pass validation and have a real trigger.

Fresh qualifying names must have one or more of:

- Near 52W low/support
- Earnings/news trigger
- Sector trigger
- Valuation comfort
- Corporate event trigger
- Important warning

Never include a fresh name just for variety.

---

### 1.16 Known Mapping Rules

Apply these mapping corrections before scoring:

- CG Power → `CGPOWER`
- WAATEE → Waaree Energies
- VSE → VST Industries / `VSTIND`
- CAPLINPOINT → `CAPLIPOINT` where required by source naming
- COSMOFE → `COSMOFIRST`
- NESTLEINDIA → `NESTLEIND`

If a mapped stock cannot be verified, use `Data Check / No score` or stock name/mapping issue. Do not guess.

Known unlisted/upcoming IPO/theme names should be treated as `Theme Watch`, not incorrect names.

---

### 1.17 Section 3 Count Summary Rules

Section 3 must summarize the full universe by action bucket.

Use compact counts for:

- Accumulate
- Watch for Dip
- Breakout Watch — no chase / retest only
- Tactical Event Play
- Deep Dive Needed
- Avoid Fresh Buy
- Data Check / No score
- Theme Watch
- Neutral / not shown after internal scan

The full watchlist universe must be covered in counts even if Section 2 is capped.

---

### 1.18 GitHub Save Rules for Phase 1

Display the full useful report in chat first.

Only after displaying the report, save the exact clean markdown to:

`Johnybritto/Market_phase1_report`

Filename format:

`phase1_YYYY-MM-DD.md`

GitHub save can be marked Success only if:

- Report contains all three required sections
- Section 2 has at least 8 real stock rows
- No placeholder-only rows
- Score columns use only 0–100 integers or `No score`
- Current Price includes source basis or clear no-score reason
- Actions follow the fixed taxonomy
- Every Action has a trigger/reason
- Breakout Watch rows contain retest/support or `no chase`
- Neutral Track Only clutter is excluded from Section 2
- GitHub markdown has no broken internal citation markers

If the report is diagnostic-only, incomplete, placeholder-heavy or format-broken, do not save it as a successful Phase 1 file.

---

## 2) Phase 2 Rules — User Selection Step

### 2.1 Purpose

Phase 2 is not a report generation phase. It is the user-input step between Phase 1 and Phase 3.

The user reviews Phase 1 and selects one or more stocks for deeper examination.

---

### 2.2 What the User Can Ask in Phase 2

The user may ask for:

- Phase 3 deep dive on a specific stock
- Comparison between two or more stocks
- Entry-range check
- Risk check
- Debt check
- Earnings check
- Valuation comfort check
- Whether to buy, wait, hold, reduce or avoid
- Whether existing portfolio exposure creates concentration risk

---

### 2.3 Phase 2 Output Rules

Phase 2 responses should be short and directive.

They should clarify:

- Whether the stock deserves Phase 3
- What exact question Phase 3 should answer
- Whether the issue is price, valuation, earnings, debt, governance, event risk, or technical setup

Phase 2 should not pretend to be a full Phase 3 deep dive.

---

## 3) Phase 3 Rules — Deep-Dive Report

### 3.1 Purpose

Phase 3 is the detailed stock deep dive for selected stocks.

It should be thorough, decision-oriented and specific to the selected stock.

A report should not be called a full Phase 3 if it only covers one theme such as data centres, defence, EMS, cooling or AI. Such reports must be labelled as a focused theme deep dive unless the complete checklist below is covered.

---

### 3.2 Mandatory Phase 3 Sections

A Phase 3 report should cover:

1. Business overview
2. Segment / revenue mix
3. Industry theme and long-term opportunity
4. Theme validation and thesis-disproof checklist
5. Latest quarterly and annual earnings
6. Revenue, EBITDA, margins, PAT, EPS and YoY/QoQ trend
7. Segment performance
8. Earnings beat/miss versus expectations where available
9. Management commentary and future signals
10. Earnings-call / investor-presentation highlights where available
11. Whether earnings support or weaken the thesis
12. Order book / pipeline where relevant
13. Cash flow, receivables, debtor days and working-capital quality
14. Debt, leverage and balance-sheet risk
15. Valuation versus peers / industry
16. Technical setup: trend, support, resistance and 52W position
17. Stock-specific news and sector news
18. Magazine-style mentions, long-form features or current news mentions
19. Institutional / smart-money evidence where available
20. Political connection, governance concern, legal/regulatory case or promoter risk
21. Event risk: geopolitical, election, war, regulatory, commodity, currency or sector-specific
22. Worst-case scenario
23. Timing and entry plan
24. Three buy-range views
25. Final action

---

### 3.3 Theme Validation and Thesis-Disproof Rules

For every Phase 3 linked to a theme such as data centres, cooling, liquid cooling, EMS, defence, railways, water, power equipment, AI, semiconductors, exchanges/platforms, renewables, ethanol, manufacturing or any other major narrative, include a dedicated **Theme Validation** block.

This block must answer these questions directly:

| Question | Required Phase 3 treatment |
|---|---|
| What percentage of revenue directly links to the theme? | Quantify from disclosed revenue where possible. If not disclosed, estimate carefully from order book, segment mix or management commentary and label it as an estimate. |
| Is revenue recurring or project-based? | Separate recurring, product, consumable, services, AMC, licensing, order-book and one-off project revenue. |
| Is operating cash flow keeping pace with profit? | Compare CFO with PAT/EBITDA and comment on cash conversion quality. |
| Are receivables rising faster than revenue? | Compare receivable growth, debtor days and working-capital trend with revenue growth. |
| Is there proprietary technology or only services/implementation? | Separate owned product/IP from system integration, EPC, MEP, trading, assembly or implementation. |
| Does the company have patents/IP or only assembly? | Mention patents, R&D, certifications, design ownership, process know-how, licensing, JV or partner dependency where available. |
| Is the theme already priced into valuation? | Compare current valuation with earnings growth, peers, 52W position, historical valuation and theme maturity. |
| What single metric would disprove the thesis? | Define one measurable metric that would break or weaken the investment thesis. |
| Is growth driven by policy, price, volume or execution? | Classify the growth driver clearly instead of only saying the theme is strong. |
| Is the company a first-order or second-order beneficiary? | First-order means direct revenue/profit from the theme. Second-order means indirect supplier, component, MEP/EPC, services, financing, distribution or optionality exposure. |

If these answers cannot be validated, Phase 3 must say **Not disclosed / Not proven** instead of guessing.

For theme stocks, the report must clearly separate:

1. Actual current revenue/profit exposure
2. Management's future plan
3. Market narrative / optionality
4. What is proven versus what is only possible
5. What would disprove the thesis

---

### 3.4 Phase 3 Buy-Range Rules

Phase 3 must include three separate buy-range views:

1. **Fundamental buy range** — based on valuation, earnings and business quality.
2. **Deep technical buy range** — based on chart support, retest zones and downside levels.
3. **Event-risk-adjusted buy range** — based on current market/event risk and margin of safety.

The report must also state which buy-range view should be prioritized.

---

### 3.5 Phase 3 Debt and Risk Rules

Always explicitly discuss:

- Debt level
- Leverage trend
- Interest burden where relevant
- Cash conversion
- Pledge risk if any
- Liquidity risk if any
- Governance/legal/regulatory concern if any
- Worst-case stock scenario

Do not ignore debt even for high-growth or popular stocks.

---

### 3.6 Phase 3 Management and Earnings Rules

Always highlight:

- What beat expectations
- What missed expectations
- What management is signaling about the future
- Whether guidance is credible
- Whether earnings quality supports the thesis
- Whether cash flow supports reported profit

---

### 3.7 Phase 3 Portfolio Context Rules

When the user already owns a related stock, include concentration risk.

Example:

If analyzing Kaynes, consider the user's existing PGEL / PG Electroplast holding because both sit in the broader EMS/electronics manufacturing exposure bucket, even though their businesses are not identical.

For cooling/data-centre names, compare exposure overlap across Blue Star, PGEL, Schneider Electric Infrastructure, Aeroflex, KRN Heat Exchanger, Voltas, Amber, data-centre power-infra names and EMS names where relevant.

---

### 3.8 Phase 3 Final Action Rules

The final action should be clear and use decision language such as:

- Buy now only if valuation and technical setup justify it
- Accumulate in staggered manner
- Wait for dip
- Buy only on retest
- Hold existing position
- Avoid fresh buy
- Reduce / exit if thesis is broken

The final action must include:

- Time horizon
- Entry plan
- Risk level
- What would change the view
- What single metric would disprove the thesis

---

## 4) Quality Principles Across All Phases

- Accuracy is more important than speed.
- Do not guess prices, symbols or mappings.
- Do not publish price-sensitive scores when price validation fails.
- Do not let GitHub saving become the main output.
- Do not save blank, placeholder-heavy or diagnostic-only reports as successful reports.
- Keep Phase 1 clean and actionable.
- Keep Phase 2 short and user-driven.
- Keep Phase 3 thorough and decision-grade.
- For theme stocks, always separate current proven exposure from future optionality.
- For high-valuation stocks, explicitly check whether the theme is already priced in.

---

## 5) Current Operating Summary

Phase 1 gives the daily shortlist.

Phase 2 is the user's selection step.

Phase 3 gives the full investment decision framework.

The workflow should prioritize useful information in chat first, then GitHub saving second.
