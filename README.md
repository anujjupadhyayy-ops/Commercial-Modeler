
# Commercial Modeler

Price a consulting deal end to end — and know in seconds whether it's worth chasing. An interactive, browser-based model spanning resource-level costing, pricing strategy, multi-year support, third-party pass-through and portfolio margin.

Built to show how **commercial structure, not just day rates, drives profitability.** Open it, edit the pre-loaded sample deal, and watch every number move.

> **No backend. No database. No accounts. Nothing leaves your browser.** A single self-contained HTML file.

---

## What it answers

*"How does this deal make money — and is it worth chasing?"*

The structure it models: **Portfolio › Product › Opportunity › Phase › resource-line.** When you cost a deal you assign it to a Product and Portfolio (example data), so individual deals roll up into a portfolio P&L.

## What you can do

- **Phases & resource lines** — unlimited phases, each with resource-type lines (days, cost/day, margin%, derived sell/day). Edit cost, margin *or* sell — the other two follow.
- **Pricing models** — Fixed price, T&M, Capped T&M.
  - *T&M* bills billable days (billable = paid × utilisation); the client absorbs overrun.
  - *Fixed price* = costed effort + margin, billed at milestone triggers; utilisation does not apply; overrun is the provider's risk.
  - *Capped T&M* bills actuals up to a ceiling, then the provider absorbs.
- **Multi-year support (AMS)** — a recurring annuity; yearly revenue = `retainer × (1 + uplift)^(year − 1)`.
- **Cost of Sale (CoS)** — a parent category with **two distinct sub-lines, never blended**: (1) Pre-Sales / BD win cost, (2) 3PP pass-through cost.
- **3PP pass-through** — third-party items resold at a markup; adds revenue at low margin, so **blended margin ≤ services margin**.
- **Invoicing profile** — a milestone billing schedule (name · trigger event · % of sell), validated to reconcile to 100%.
- **Win probability & pursue decision** — a pWin slider captures winnability as a judgement kept *separate* from the economics. The top summary strip gives the punchline: TCV, margin, win %, and a **Pursue / Qualify / Drop** call driven by margin quality × winnability. Win-weighted **expected margin** appears only in the portfolio view.
- **Portfolio mode** — toggle deals on/off to see each one's marginal effect on portfolio revenue, margin and expected margin.

## Key formulae

```
sell/day        = cost/day ÷ (1 − margin)
build revenue   = Σ(billable days × sell/day)        [T&M / Capped]
                = Σ(days × sell/day)                  [Fixed, no utilisation]
support revenue = Σ_years retainer × (1 + uplift)^(y−1)
3PP revenue     = Σ 3PP cost × (1 + markup)
CoD             = build delivery cost + support cost
CoS             = Pre-Sales cost + 3PP cost           (shown separately)
TCV             = services revenue + 3PP revenue
margin          = TCV − CoD − CoS
blended margin  = (services margin + 3PP markup) ÷ total revenue
blended rate    = build revenue ÷ billable days       (single average £/day)
expected margin = margin × win probability            (portfolio view only)
```


## Technical notes

- Single-file HTML/CSS/JS; **[Chart.js](https://www.chartjs.org/)** from CDN is the only dependency.
- Fully client-side; all state lives in browser memory for the session.
- Responsive — stacks to a single column on mobile.

## Disclaimer

Illustrative sample model for demonstration — not financial, accounting or commercial advice. Do not enter real client data; page source is public on any static host.

*Illustrative Sample Model — Developed with Claude · By Anuj Upadhyay*
