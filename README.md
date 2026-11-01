# House vs Market

Is buying a home worth it, or would the same money do better in the market while you rent?

**Live site:** https://crabtofu.github.io/house-worth-it/

House vs Market is an interactive calculator for UK home buyers. It follows the same starting capital down two routes:

- **House path:** buy the home, invest the rent you no longer pay, and cover the running costs (service charge, maintenance, stamp duty and fees, and an optional mortgage).
- **Invest path:** put all the cash in the market and leave it untouched. Rent comes out of the same income the owner invests instead.

It then works out the **break-even market return**: the yearly return at which both routes finish with the same wealth. If your expected return is above it, investing wins. Below it, the house wins.

## What's on the page

- **Break-even:** the verdict, a scale showing your assumed return against the break-even, and a plain-English breakdown of each path. The breakdown covers what you put in, the rent saved and reinvested, what that earns, the costs, and what would change the answer.
- **Charts:** net wealth for each path year by year (with the year one path overtakes the other), the gap between the paths at every market return, and a full year-by-year table.
- **Assumptions:** sliders for the house, mortgage, holding period, market return and tax. Everything updates as you move them, and your settings are saved in your browser.
- **Export:** "Copy for AI" copies your assumptions, results and yearly cash flows as text, ready to paste into a chat with Claude for deeper analysis.
- Light and dark themes, plus a "Today's money" switch to show every figure after inflation.

## How the model works

- Cash flows land at the end of each year.
- Rent is counted once, as the owner's saving. The owner invests the rent they don't pay, less running and mortgage costs, into a cash pot that earns the market return. The renter's portfolio is never touched. Counting rent on both sides would double it. The "i" next to the invest path on the page explains why this is fair.
- Rent is the rental yield times the starting house price. Rent and running costs can rise with inflation.
- Selling costs and tax on gains are charged once, in the year you cash out.
- The break-even return is found by searching market returns from −5% to 30% a year.

**Not modelled:** income tax on dividends, council tax, insurance, empty periods, changes to ground rent, and year-to-year swings in market returns. The market return is a steady average.

## Not financial advice

This is a planning tool, not financial advice. Your capital is at risk: markets and house prices can fall, and you could get back less than you put in.

## Running it locally

It's a single self-contained `index.html` with no build step. Open it in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000. Fonts load from Google Fonts. Everything else is inline.

## Deploying

The site is served by GitHub Pages from the `main` branch. Every push to `main` redeploys it automatically, usually within a minute or two.
