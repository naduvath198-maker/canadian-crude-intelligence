# Canadian Crude Market Intelligence — Portfolio Website

Interactive, dependency-free static website built for a commercial and customer-experience energy analytics portfolio.

## Important data disclaimer
The supplied WTI, WCS, and USD/CAD observations in `index.html` are **synthetic demonstration values**, not real market observations. Before sharing it as market research, replace them with sourced, verified data using the CSV import available under **Data & Methodology**. Verify period, units, benchmark definitions and observations against the cited official sources. The website shows imported data as *unverified* until you separately check it.

## Preview locally
Open `index.html` in any recent browser. No server or installation is required. If your browser restricts opening local HTML files, run `python -m http.server 8000` inside this folder and open `http://localhost:8000`.

## Publish it on GitHub Pages
1. Create a public GitHub repository named `canadian-crude-intelligence`.
2. Upload `index.html` into the repository root. You may optionally include README and the demo CSV.
3. Navigate to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, **main**, folder **/(root)**, and save.
5. GitHub Pages should provide a URL like `https://YOUR-USERNAME.github.io/canadian-crude-intelligence/`. That is an example, **not an active website URL**. Confirm the actual address in the repository's Pages settings.

The dashboard is published as a GitHub repository; enable GitHub Pages under Settings → Pages to make it publicly accessible.

## Accepted CSV schema
`Month,WTI_USD_bbl,WCS_USD_bbl,USD_CAD`

Example (fictitious):
```csv
Month,WTI_USD_bbl,WCS_USD_bbl,USD_CAD
2026-08,73.00,57.00,1.3800
2026-09,72.00,55.00,1.3900
```
Monthly observations must be aligned to the same period. CSV imports affect the browser's session only; they do not rewrite the website for other visitors. For a **permanent public portfolio with verified data**, replace the `DEMO` initial array in `index.html` with audited monthly values or edit the site to load a committed verified CSV. Don't claim it is historical until that change is made.

## Metrics
- WCS discount (USD/bbl) = WTI − WCS
- WCS discount % = (WTI − WCS) / WTI
- Modeled gross revenue (CAD) = MAX(0, WTI − WCS discount) × (CAD per USD) × saleable bbl/day × period days
- Scenario omits operating costs, royalties, transportation, realized quality differentials, hedging and other limitations.

## Sources
- Alberta WCS/WTI: https://economicdashboard.alberta.ca/dashboard/wcs-oil-price
- Alberta Open Government Energy Prices: https://open.canada.ca/data/en/dataset/6dc97b50-5bbb-482d-8dd5-c9b23cd770dc
- Bank of Canada monthly FX: https://www.bankofcanada.ca/rates/exchange/monthly-exchange-rates/

Independent portfolio illustration — not affiliated with S&P Global, Platts, or SLB.