# Egypt E-commerce Web Scrapers

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB)
![Node.js](https://img.shields.io/badge/Node.js-20%2B-339933)
![Scrapers](https://img.shields.io/badge/Scrapers-39-blue)

A curated collection of 39 Python and JavaScript scrapers for Egyptian retail and e-commerce websites. Every project provides one focused scraper, concise instructions, and 10 cleaned sample records in a shared product schema.

> [!IMPORTANT]
> Website structures and policies change. Review the target website's terms, robots policy, and rate limits before running any scraper.

## Key features

- 39 independently runnable retailer scrapers
- Python and JavaScript implementations
- Static HTML, API, sitemap, GraphQL, and browser-automation strategies
- Consistent cleaned sample schema across all projects
- Minimal project folders with no debug scripts or full datasets
- Shared dependency files and detailed technical documentation

## Repository architecture

```text
Ecommerce-Scrapping-Egypt-2026/
├── scrapers/
│   └── <retailer>/
│       ├── scraper.py | scraper.js   # Final scraper
│       ├── sample_data.csv           # 10 cleaned records
│       └── README.md                 # Project instructions
├── .gitignore                        # Generated-file exclusions
├── DOCUMENTATION.md                  # Technical reference
├── LICENSE                           # MIT License
├── package.json                      # JavaScript dependencies
├── requirements.txt                  # Python dependencies
└── README.md                         # Project overview
```

Each retailer folder is independent. There is no global runner and no hidden dependency between scraper folders.

## Quick start

### Python scraper

```powershell
git clone https://github.com/belalhazem511/Ecommerce-Scrapping-Egypt-2026.git
cd Ecommerce-Scrapping-Egypt-2026

python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
playwright install chromium

cd scrapers/ariika
python scraper.py
```

On macOS or Linux, activate the environment with `source .venv/bin/activate`.

### JavaScript scraper

```powershell
git clone https://github.com/belalhazem511/Ecommerce-Scrapping-Egypt-2026.git
cd Ecommerce-Scrapping-Egypt-2026

npm install
npx playwright install chromium

cd scrapers/dream2000
node scraper.js
```

Always read the retailer folder's README and inspect the scraper settings before starting a full run.

## Data contract

Every `sample_data.csv` contains exactly 10 unique cleaned products using this schema:

| Column | Description |
|---|---|
| `name` | Product name |
| `price` | Current numeric price |
| `old_price` | Previous numeric price, when available |
| `discount` | Source discount value |
| `category` | Product category or path |
| `brand` | Product brand |
| `url` | Product page URL |
| `image_url` | Product image URL |
| `availability` | Stock status reported by the source |
| `seller` | Retailer, marketplace, or pharmacy |

Optional values remain blank when the source does not provide reliable data. The samples demonstrate structure and are not current or complete product catalogs.

## Technology

The collection uses tools appropriate to each target:

- Requests, HTTPX, aiohttp, Beautiful Soup, and lxml
- Playwright and Selenium for rendered pages
- Public JSON, GraphQL, sitemap, and storefront endpoints
- pandas and CSV/JSON exports for data processing

See [DOCUMENTATION.md](DOCUMENTATION.md) for the scraper catalog, cleaning rules, quality checklist, troubleshooting, security, and maintenance guidance.

## Responsible use

- Collect only public data you are permitted to access.
- Keep request delays and concurrency at respectful levels.
- Stop on access-denied or rate-limit responses.
- Do not bypass authentication, CAPTCHA, or technical restrictions.
- Never commit credentials, cookies, browser profiles, or generated datasets.
- Validate output before using it for analysis or business decisions.

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2026 Belal Hazem.
