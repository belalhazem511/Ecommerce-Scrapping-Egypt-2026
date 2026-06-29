# Egypt E-commerce Web Scrapers

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB)
![Node.js](https://img.shields.io/badge/Node.js-20%2B-339933)
![Scrapers](https://img.shields.io/badge/Scrapers-39-blue)

A curated collection of 39 Python and JavaScript scrapers for Egyptian retail and e-commerce websites. Each retailer project provides one focused scraper, concise instructions, and 10 cleaned example records in a shared product schema.

> [!IMPORTANT]
> Website structures and policies change. Review the target website's terms, robots policy, and rate limits before running any scraper.

## Features

- **39 retailer projects:** independently runnable and easy to inspect
- **Multiple extraction strategies:** HTML, public API, GraphQL, sitemap, storefront, and browser automation
- **Static and dynamic support:** lightweight HTTP clients for static sources and browser engines for rendered pages
- **Concurrent collection:** async requests or worker pools where supported by the target
- **Pagination and discovery:** category, sitemap, search, and product URL workflows
- **Normalized product examples:** the same 10-column sample contract in every project
- **Data cleaning:** trimmed text, numeric price fields, URL validation, and duplicate removal
- **Operational resilience:** timeouts, retry patterns, checkpoints, or resume behavior in applicable scrapers
- **Source-control hygiene:** generated datasets, logs, caches, browser profiles, and secrets are excluded
- **Project-level guidance:** every retailer folder documents requirements and execution

Feature availability varies by scraper because each website exposes different capabilities.

## Architecture

```text
Ecommerce-Scrapping-Egypt-2026/
|-- scrapers/
|   `-- <retailer>/
|       |-- scraper.py | scraper.js   # Final scraper
|       |-- sample_data.csv           # 10 cleaned example records
|       `-- README.md                 # Retailer-specific instructions
|-- .gitignore                        # Generated-file exclusions
|-- DOCUMENTATION.md                  # Technical reference
|-- LICENSE                           # MIT License
|-- package.json                      # JavaScript dependencies
|-- requirements.txt                  # Python dependencies
`-- README.md                         # Project overview
```

Each retailer folder is isolated. There is no global runner or hidden dependency between scraper folders.

## Technology stack

| Area | Technologies | Purpose |
|---|---|---|
| Languages | Python 3.11+, JavaScript, Node.js 20+ | Scraper implementation |
| HTTP clients | Requests, HTTPX, aiohttp, Axios | HTML, XML, and API requests |
| HTML parsing | Beautiful Soup, lxml, Cheerio | Static document extraction |
| Browser automation | Playwright, Selenium | JavaScript-rendered websites |
| Data sources | REST, GraphQL, sitemaps, storefront APIs | Product discovery and extraction |
| Data processing | pandas, CSV, JSON | Cleaning, normalization, and export |
| Concurrency | asyncio, aiohttp, worker pools | Controlled parallel collection |
| Version control | Git and GitHub | Source history and collaboration |

Not every project uses every technology. Each scraper uses the smallest practical stack for its target.

## Prerequisites

Install the tools required for the scraper language:

- Git
- Python 3.11 or newer
- Node.js 20 or newer and npm
- Internet access
- Chromium, installed through Playwright, for browser-based projects

Verify the main tools:

```powershell
git --version
python --version
node --version
npm --version
```

## Setup

### 1. Clone the repository

```powershell
git clone https://github.com/belalhazem511/Ecommerce-Scrapping-Egypt-2026.git
cd Ecommerce-Scrapping-Egypt-2026
```

### 2. Set up Python

Windows PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
playwright install chromium
```

macOS or Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
playwright install chromium
```

### 3. Set up JavaScript

```powershell
npm install
npx playwright install chromium
```

### 4. Verify the environment

```powershell
python -c "import requests, bs4, pandas; print('Python dependencies ready')"
node -e "require('playwright'); console.log('Node dependencies ready')"
```

## Run a scraper

Always run a scraper from its own directory so relative output paths work correctly.

Python example:

```powershell
cd scrapers/ariika
python scraper.py
```

JavaScript example:

```powershell
cd scrapers/dream2000
node scraper.js
```

Before a full run:

1. Read the retailer folder's README.
2. Review target URLs, output paths, request delay, concurrency, and browser settings.
3. Use a small product or page limit when the scraper supports one.
4. Inspect the first output records before continuing.

## Data contract

Every `sample_data.csv` contains exactly 10 unique cleaned products:

| Column | Description |
|---|---|
| `name` | Product name |
| `price` | Current numeric price |
| `old_price` | Previous numeric price, when available |
| `discount` | Discount value reported by the source |
| `category` | Product category or category path |
| `brand` | Product brand |
| `url` | Product page URL |
| `image_url` | Product image URL |
| `availability` | Source stock status |
| `seller` | Retailer, marketplace, or pharmacy |

Optional values remain blank when the source does not provide reliable data. Samples demonstrate structure and are not current or complete catalogs.

## Documentation

Read [DOCUMENTATION.md](DOCUMENTATION.md) for:

- Complete scraper catalog
- Cleaning and deduplication rules
- Data-quality checklist
- Extraction architecture and data flow
- Reliability and maintenance guidance
- Troubleshooting and security practices

## Responsible use

- Collect only public data you are permitted to access.
- Keep request delays and concurrency at respectful levels.
- Stop on access-denied or rate-limit responses.
- Do not bypass authentication, CAPTCHA, paywalls, or technical restrictions.
- Never commit credentials, cookies, browser profiles, or generated datasets.
- Validate output before using it for analysis or business decisions.

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2026 Belal Hazem.
