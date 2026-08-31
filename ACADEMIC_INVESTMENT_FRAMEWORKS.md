# Academic Investment Frameworks — Mandatory Investment Analysis Rules

**Last updated:** 31 August 2026  
**Repository:** `Johnybritto/Market_phase1_report`  
**Status:** AUTHORITATIVE FRAMEWORK MASTER  
**Applies to:** Phase 1, Phase 3, portfolio/holdings reviews, stock comparisons, entry/averaging decisions, sell/trim decisions, macro-event impact analysis and capital-allocation decisions.

---

## 0. Purpose and Hierarchy

This file converts selected academic finance frameworks into practical rules for the investment workflow.

It is a mandatory implementation companion to:

- `MASTER_INVESTMENT_RULES.md` — top-level investment decision authority.
- `PHASE_1_2_3_RULES.md` — Phase 1 / Phase 2 / Phase 3 operating specification.
- `PORTFOLIO_HOLDINGS.md` — current portfolio source of truth.

### Single-source rule

The detailed academic-framework logic must live **only in this file**. Do not scatter separate versions into chat memory, daily reports, holdings files or unrelated markdown files.

Other master files should reference this file rather than duplicate its contents. If this file is changed, future analyses must use the latest repository version.

### Pre-analysis rule

Before producing any of the following, read this file together with the applicable master rules:

- Full Phase 3 deep dive.
- Portfolio/holdings review.
- Buy / average / add-more decision on an existing holding.
- Sell / trim / exit decision.
- Comparison between two stocks where capital allocation is involved.
- Macro-event or market-event impact on the portfolio.
- Phase 1 decision where one of the framework triggers below is material.

The frameworks are decision aids, not substitutes for current facts, company filings, earnings, valuation or technical evidence.

---

## 1. Mandatory Visible Attribution Rule

Whenever one of the frameworks materially affects a conclusion, the answer must visibly identify it.

Use this format:

`**[Framework: <Framework / Author> | Impact: Positive / Negative / Mixed / Risk-control | Confidence: High / Medium / Low]**`

Then state in plain language:

1. What the framework is telling us.
2. Which current evidence triggered it.
3. How it changes the investment decision.

Example:

`**[Framework: Limits to Arbitrage — Shleifer & Vishny | Impact: Risk-control | Confidence: Medium]** The stock may be undervalued, but there is no visible catalyst and liquidity is weak. Cheapness alone is therefore not a reason to average immediately; wait for earnings/cash-flow confirmation or a technical stabilisation.`

### Attribution discipline

- Do not attach a framework label merely to make the report look sophisticated.
- Do not say a theory "proves" a stock will rise or fall.
- The framework tag is mandatory only when it materially contributes to the conclusion.
- If the conclusion comes mainly from earnings, debt, cash flow or technicals, say so; do not falsely attribute it to a paper.
- Several frameworks may be applied to the same decision if each contributes something distinct.

---

## 2. Agency Theory — Jensen & Meckling

### Decision status

**USE — MANDATORY for full Phase 3 governance/capital-allocation review.**

### Practical question

> Are management/promoter incentives aligned with minority shareholders, or can insiders benefit while outside shareholders bear the cost?

### Where it is used

- Phase 3: governance, promoter risk, management quality and capital allocation.
- Sell/trim reviews when governance changes.
- Averaging decisions after a large fall.
- Comparison of otherwise similar companies.
- Long-term 5+ year core-holding classification.

### Mandatory Agency Alignment checks

Check, where data is available:

- Promoter/management ownership and changes in ownership.
- Promoter pledging.
- Promoter remuneration versus company scale and performance.
- Related-party transactions.
- Preferential allotments / warrants / repeated dilution.
- ESOP dilution where material.
- Loans, guarantees or advances to promoter-linked / related entities.
- Acquisitions with weak strategic or financial logic.
- Persistent empire-building capex with poor ROCE.
- Cash retained without productive deployment.
- Capital allocation between capex, acquisitions, debt reduction, dividends and buybacks.
- Management guidance versus actual delivery history.
- Auditor resignations / qualifications / accounting concerns.
- Sudden management or CFO changes where relevant.
- Minority-shareholder treatment in mergers, demergers, delistings or related transactions.
- Receivables/cash-conversion problems that may hide weak economic quality behind reported profit.

### Required conclusion

Classify **Agency / Alignment Risk** as:

- Low
- Moderate
- High
- Severe

Do not use a numeric score unless enough evidence exists to justify one.

### Decision effect

- High or Severe agency risk can override an attractive theme or valuation.
- A falling share price is **not** an averaging opportunity if agency risk is unresolved.
- A premium valuation is easier to justify when management has a strong history of minority-shareholder alignment and disciplined capital allocation.

### Required visible label when material

`[Framework: Agency Theory — Jensen & Meckling]`

---

## 3. Market Efficiency / Efficient Markets — Eugene Fama

### Decision status

**USE — MANDATORY as a Priced-In / Information-Edge test for full Phase 3 and major event-driven decisions.**

### Practical question

> Is our investment thesis genuinely differentiated, or are we simply repeating public information the market already knows?

### Where it is used

- Phase 3 valuation and theme validation.
- New-order / new-capacity / policy / earnings announcements.
- Breakout or momentum decisions.
- Magazine/news-derived stock ideas.
- Phase 1 when a widely publicised catalyst is driving price.
- Comparisons where one stock appears "obviously" better because of well-known news.

### Mandatory Priced-In Test

For every material thesis, separate:

1. **Known public information** — orders, capex plan, policy tailwind, capacity, management guidance, announced product, etc.
2. **Likely market expectation** — what investors appear already to be paying for.
3. **Our differentiated insight** — what is not merely a repetition of the public narrative.
4. **Evidence for the differentiated insight** — earnings, margins, cash conversion, utilisation, competitive advantage, channel data, valuation gap, execution track record, etc.
5. **What would prove our edge wrong.**

### Required conclusion

State one of:

- **Not priced in / partially priced in** — evidence suggests expectations remain below realistic outcomes.
- **Largely priced in** — thesis is valid but valuation already discounts much of it.
- **Overpriced narrative** — expectations appear to require unusually optimistic outcomes.
- **No identifiable edge** — public information is known and there is no differentiated conclusion yet.

### Decision effect

- Public news alone cannot be treated as an investment edge.
- A great company can still be a poor fresh buy if the market already discounts the great outcome.
- If there is no identifiable edge, the default should shift toward `Watch for Dip`, `Deep Dive Needed` or no fresh action rather than forced buying.

### Required visible label when material

`[Framework: Market Efficiency — Eugene Fama]`

---

## 4. Limits to Arbitrage — Shleifer & Vishny

### Decision status

**USE — MANDATORY when the thesis depends on a stock being mispriced, excessively cheap, excessively expensive or sentiment-dislocated.**

### Practical question

> Even if the market price is wrong, what makes the mispricing close — and how much pain can occur before it does?

### Where it is used

- Entry timing.
- Averaging after a fall.
- Deep-value / turnaround situations.
- Very expensive momentum names.
- Low-liquidity / small-cap names.
- Event-driven dislocations.
- Phase 1 `Watch for Dip`, `Breakout Watch`, `Tactical Event Play` and selected `Accumulate` calls.
- Phase 3 valuation and timing sections.

### Mandatory Mispricing-Persistence Test

If analysis says a stock is undervalued or overvalued, also answer:

1. Why might the mispricing exist?
2. Why might it persist?
3. Is liquidity sufficient?
4. Is positioning/crowding amplifying the move?
5. What catalyst can close the gap?
6. Is the catalyst company-specific, earnings-driven, valuation-driven, policy-driven or merely hoped for?
7. What is a realistic time horizon for the gap to close?
8. What can happen before we are proven right?
9. Can the investor survive that path without being forced to sell?

### Catalyst classification

Classify the rerating catalyst as:

- **Visible** — identified and reasonably near-term.
- **Probable but timing uncertain**.
- **Weak / narrative-only**.
- **None identified**.

### Decision effect

- `Cheap` is never sufficient by itself for `Accumulate`.
- `Expensive` is never sufficient by itself for a short-term bearish conclusion.
- If the stock is cheap but the catalyst is absent and technical/sentiment pressure remains high, prefer staggered entry or waiting.
- If a stock is expensive but momentum, liquidity and narrative remain strong, avoid assuming valuation will correct immediately.

### Required visible label when material

`[Framework: Limits to Arbitrage — Shleifer & Vishny]`

---

## 5. Modern Portfolio Theory — Harry Markowitz

### Decision status

**USE — MANDATORY at portfolio level. Do not use it as a standalone stock-picking engine.**

### Practical question

> What does this position do to the risk of the whole portfolio, not just the attractiveness of the stock in isolation?

### Where it is used

- Weekly holdings review.
- Any recommendation to add a new stock to the portfolio.
- Any recommendation to average an existing holding materially.
- Sell/trim decisions involving concentration.
- Stock-vs-stock capital-allocation comparisons.
- Theme overlap analysis.
- Portfolio drawdown-risk analysis.

### Mandatory Portfolio Fit Test

Before recommending new capital, assess:

- Current position size.
- Sector concentration.
- Economic-theme concentration.
- Common revenue-driver exposure.
- Common customer / government-spending exposure where material.
- Common commodity/input exposure.
- Common interest-rate / currency sensitivity.
- Common market-liquidity / risk-on sensitivity.
- Historical return correlation when reliable data is available.
- Fundamental/economic correlation even when historical price correlation is low.

### Correlation rule

Historical price correlation is useful but must not be treated as permanent truth.

Where adequate price history is available, correlation can be calculated over more than one window, for example:

- 1-year daily/weekly returns.
- 3-year weekly returns.

But the final decision must also consider business-factor overlap. Two stocks can show low historical price correlation and still share the same future economic risk.

### Diversification rule

Do not call a portfolio diversified simply because it owns many tickers.

Diversification should mean **different underlying economic risks**, not merely different company names.

### Portfolio decision effect

A new stock can be fundamentally attractive but still receive a lower allocation or `Wait` if it materially duplicates an existing exposure.

Conversely, a slightly lower-return opportunity may improve portfolio resilience if it provides genuinely different economic exposure without sacrificing quality.

### No false optimisation

Do not mechanically construct a Markowitz efficient frontier and treat the result as an optimal portfolio unless data quality, return assumptions and covariance stability are good enough. Historical optimisation can create false precision.

### Required visible label when material

`[Framework: Modern Portfolio Theory — Harry Markowitz]`

---

## 6. Arbitrage Pricing Theory — Stephen Ross

### Decision status

**USE — MANDATORY as a multi-factor risk lens for portfolio and event analysis. Use factor thinking; do not force a formal academic regression unless the data genuinely supports it.**

### Practical question

> Which external economic factors can move this stock — and which factors can hurt several holdings at the same time?

### Where it is used

- Macro-event impact on holdings.
- Weekly portfolio review.
- Phase 1 Market Backdrop when a macro factor materially matters.
- Phase 3 event-risk section.
- Stock comparisons across different sectors.
- Stress testing.

### Standard factor library

Use only factors economically relevant to the company. Common factors include:

- Crude oil / energy prices.
- INR appreciation/depreciation.
- Interest rates / bond yields.
- Inflation.
- Government capex / fiscal spending.
- Private capex cycle.
- Consumer discretionary demand.
- Credit growth / liquidity.
- Capital-market activity / trading volumes.
- Commodity/input costs: copper, aluminium, steel, chemicals, etc.
- Export demand / global growth.
- Regulation / policy.
- Defence ordering cycle.
- Power / grid capex.
- Electronics / semiconductor cycle.
- Data-centre / cloud capex.
- Healthcare utilisation / pricing where relevant.

Do not include irrelevant factors simply to fill a table.

### Factor Exposure Map

For each material factor, classify:

- Direction: Positive / Negative / Mixed / Neutral.
- Sensitivity: Low / Medium / High.
- Transmission path: explain how the factor reaches revenue, margins, working capital, valuation or liquidity.
- Time horizon: Immediate / quarterly / multi-year.
- Evidence confidence: High / Medium / Low.

### Portfolio stress test

For major macro questions, identify:

1. Which holdings benefit.
2. Which holdings are hurt.
3. Which holdings have mixed/hedged exposure.
4. Where multiple positions share the same factor risk.
5. Whether the portfolio requires action or simply monitoring.

### Decision effect

Do not assume sector labels fully describe risk. A company's earnings may depend more on currency, commodity inputs, capex cycles or market liquidity than on its nominal sector.

### Required visible label when material

`[Framework: Arbitrage Pricing Theory — Stephen Ross]`

---

## 7. Workflow Integration Matrix

| Workflow | Agency Theory | Fama / Priced-In | Limits to Arbitrage | Markowitz / Portfolio | Ross / Multi-factor |
|---|---|---|---|---|---|
| Phase 1 daily scan | Triggered only for material governance issues | Use for public-news / crowded-theme catalyst | Use for mispricing, dip, breakout and catalyst timing | Use for holding/concentration warnings | Use in Market Backdrop when macro factor is material |
| Phase 2 quick decision | Use if governance is the core question | Use if question is "is news already priced?" | Use if question is "buy now or wait?" | Use for stock-vs-stock capital allocation | Use for macro-sensitive comparison |
| Full Phase 3 | **Mandatory** | **Mandatory** | **Mandatory when valuation/mispricing matters** | **Mandatory for buy/add/portfolio-fit decisions** | **Mandatory in event-risk / factor-sensitive cases** |
| Weekly holdings review | Governance changes only | Use on major rerating narratives | Use on extreme valuation/dislocation | **Mandatory** | **Mandatory** |
| Buy / average decision | Mandatory if governance concerns exist | Mandatory if thesis is widely public | Mandatory if decision relies on cheapness | **Mandatory** | Use when macro exposure matters |
| Sell / trim decision | Mandatory if governance triggers | Use when valuation assumes perfect execution | Use when waiting for mean reversion | **Mandatory** | Use when factor exposure has changed |
| Macro-event portfolio analysis | Usually not relevant | Usually secondary | Use if market dislocation creates mispricing | Use to assess portfolio concentration | **Mandatory** |
| Magazine-derived idea | Use when article promotes management/company | **Mandatory: separate article information from market edge** | Use if magazine argues cheap/expensive | Use before adding to portfolio | Use if article is macro/theme driven |

---

## 8. Phase 1 Implementation Rules

Do not add new columns to the fixed Phase 1 table solely for these frameworks.

When a framework materially changes a visible Phase 1 row, append a short attribution inside the existing `Outcome Bias` or `Action` text.

Examples:

- `Watch for Dip — public order win appears largely priced in. [Framework: Market Efficiency — Fama]`
- `Watch for Dip — undervaluation visible but no rerating catalyst yet. [Framework: Limits to Arbitrage — Shleifer & Vishny]`
- `Avoid Fresh Buy — promoter-related capital-allocation concern. [Framework: Agency Theory — Jensen & Meckling]`
- `Deep Dive Needed — adds more exposure to same capital-markets factor already in portfolio. [Framework: Modern Portfolio Theory — Markowitz]`

Keep Phase 1 concise. Full framework reasoning belongs in Phase 3 or portfolio review.

---

## 9. Phase 3 Implementation Rules

Every full Phase 3 must contain an **Academic Framework Overlay** near the final decision section.

The overlay should include only the frameworks that are relevant, but must explicitly state `Not material to this decision` for mandatory frameworks that were considered and not applicable.

Minimum Phase 3 overlay for a potential buy/add decision:

1. **Agency Theory — Jensen & Meckling:** alignment/governance conclusion.
2. **Market Efficiency — Fama:** priced-in / information-edge conclusion.
3. **Limits to Arbitrage — Shleifer & Vishny:** mispricing/catalyst conclusion if valuation gap is part of thesis.
4. **Modern Portfolio Theory — Markowitz:** portfolio overlap/concentration conclusion.
5. **Arbitrage Pricing Theory — Ross:** material factor exposures and common portfolio risks.

### Phase 3 decision bridge

The overlay must end with:

`Framework impact on final action:`

Then explain in 1–3 sentences whether the frameworks strengthen, weaken or do not change the fundamental/technical conclusion.

The final action remains driven by the complete evidence set; frameworks do not automatically override verified business fundamentals unless they expose a major risk such as governance failure or portfolio concentration.

---

## 10. Weekly Holdings / Portfolio Review Rules

Every full holdings review must include:

### A. Correlation / concentration map — Markowitz

Identify clusters that may behave like one economic bet even when company names differ.

### B. Factor exposure map — Ross/APT

Identify the portfolio's largest common sensitivities and what current macro changes mean for them.

### C. Agency-risk changes — Jensen & Meckling

Only highlight holdings where new governance/capital-allocation evidence has changed.

### D. Priced-in / narrative risk — Fama

Flag holdings where valuation appears to assume a widely known bullish narrative with little room for disappointment.

### E. Mispricing / catalyst check — Shleifer & Vishny

For holdings down materially or trading far from assessed value, state whether a catalyst exists and whether immediate averaging is justified.

---

## 11. Comparison and Capital-Allocation Rules

When comparing two or more stocks for where to put the next rupee, do not stop at business quality or valuation.

Also compare:

- Agency/alignment risk.
- What is already priced into each stock.
- Whether valuation gaps have a credible catalyst.
- Which stock adds or duplicates portfolio risk.
- Which macro factors drive each stock.

If the framework changes the winner, explicitly say so with the visible framework attribution.

---

## 12. What We Deliberately Do NOT Implement

### Black–Scholes

Not part of the core cash-equity workflow. Use only if the analysis expands to options, warrants or option-like securities where option valuation is genuinely relevant.

### CAPM / Sharpe

Do not use CAPM as a primary stock-selection, ranking or Phase 1 scoring model.

CAPM may be used quietly as one input to cost of equity / discount rate in a DCF or valuation cross-check where appropriate. If CAPM materially changes a valuation conclusion, explain the assumption rather than presenting the output as objective truth.

---

## 13. Guardrails Against Pseudo-Precision

- Academic models do not convert uncertain assumptions into facts.
- Do not manufacture exact expected returns from weak data.
- Do not use historical beta/correlation as a permanent forecast.
- Do not assign precise factor sensitivities without evidence.
- Do not claim a stock is mispriced merely because our valuation differs from market price.
- Do not confuse a popular theme with an information edge.
- Do not use an academic label to override contradictory earnings/cash-flow evidence.
- When evidence is insufficient, state `Not proven` or `Low confidence`.

---

## 14. Completeness Check

For any full Phase 3, portfolio review or major capital-allocation decision, verify:

- [ ] Agency / management alignment considered.
- [ ] Priced-In / information-edge test considered.
- [ ] Mispricing persistence and catalyst considered where valuation gap is part of thesis.
- [ ] Portfolio correlation / overlap considered before adding capital.
- [ ] Material macro-factor exposures considered.
- [ ] Every framework that materially changed the conclusion is visibly attributed.
- [ ] No framework is cited where it did not actually contribute.
- [ ] No false mathematical precision introduced.

---

## 15. Core Principle

> **Use academic finance to expose risks and improve decisions, not to decorate reports. A framework earns a place only when it changes what we look for, what we measure, or what we do with capital.**