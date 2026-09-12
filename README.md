# MAO Desk — Wholesale Underwriting Calculator

A single-file underwriting desk for residential wholesaling. Derives the Maximum Allowable Offer backward from what a cash buyer can actually pay, then pressure-tests the contract across five exit strategies and a line-item repair scope.

Everything runs client-side in one `index.html`. No build step, no backend, no data leaves the browser.

## What it does

**MAO solved from the buyer's position.** ARV minus repairs, holding, buy-side closing, sell-side closing, and the buyer's required profit produces the end-buyer's maximum price. Subtract your assignment fee for MAO. Buy-side closing depends on price, so the model iterates to convergence.

Four buyer-requirement methods: target profit as a % of ARV, a flat dollar profit, a target ROI on cash (solved algebraically), or the classic 70% rule.

**Seven tabs**

| Tab | Purpose |
| --- | --- |
| Flip / Wholesale | Offer waterfall and end-buyer deal math |
| Repair Scope | 40+ line items, age triggers, bid locks, scope exports |
| Closing Costs | Itemized buy and sell side, percentage or flat per line |
| Rental & DSCR | NOI, DSCR, max loan at target DSCR, BRRRR cash-left-in, 1% rule |
| Wholetail | List-price comparison with a deferred-repair discount guard |
| Seller Finance | Wrap spread, day-one cash, balloon balances, note present value |
| Sensitivity | ARV and repair swings at ±5% and ±10% with margin shading |

**Repair scope estimator.** Quantities auto-derive from living area, roofing squares, bath count, and carpeted area. Five scope presets, a cost-basis multiplier for investor vs. retail pricing, per-line bid locks that bypass the multiplier, useful-life triggers for roof/HVAC/water heater, and vintage flags driven by year built. Overlap detection catches double-counted lines. Exports a priced CSV, a saved-scope JSON, and a request-for-bid scope of work with quantities but no prices.

**Holding costs** in three modes: flat monthly, % of ARV per year, or itemized taxes, insurance, utilities, and hard-money interest.

**PDF deal summary.** Up to five pages via jsPDF, with per-page disclaimers and optional sections for repair scope, rental, wholetail, and seller-finance exits.

## Use it

Open `index.html` in any browser, or visit the GitHub Pages URL for this repo.

## Assumptions worth knowing

Unit costs reflect investor-grade Houston pricing as of 2026 and run well below retail contractor quotes — that is what the cost-basis multiplier is for. Per-square-foot benchmark bands are approximate: cosmetic $8–20, light $20–32, moderate $32–52, heavy $52–72, gut $72–100.

Nothing here is an appraisal, inspection, loan commitment, or guarantee of profit. Verify ARV, scope, rents, and carrying costs independently before contracting.

## Dependencies

- [jsPDF 2.5.1](https://github.com/parallax/jsPDF) via cdnjs, for PDF export
- Satoshi via [Fontshare](https://www.fontshare.com)

## License

Private. All rights reserved.
