# Web scraping scripts

A simple collection of 39 website scrapers.

See [DOCUMENTATION.md](DOCUMENTATION.md) for complete setup, data schema, quality, maintenance, and responsible-use guidance.

Each folder inside `scrapers` contains only:

- One final `scraper.py` or `scraper.js`
- One `sample_data.csv` with 10 cleaned example products
- One `README.md` with instructions

Old versions, tests, debug scripts, cached pages, datasets, archives, and helper files were removed from this GitHub copy. The original workspace was not changed.

All samples use the same columns: name, price, old price, discount, category, brand, product URL, image URL, availability, and seller. Blank optional values mean that field was not available in the source data.

## Install

For Python scrapers:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
playwright install chromium
```

For JavaScript scrapers:

```powershell
npm install
npx playwright install chromium
```

## Run a scraper

Open the required folder and read its README:

```powershell
cd scrapers/ariika
python scraper.py
```

or:

```powershell
cd scrapers/dream2000
node scraper.js
```

## Important

- Review the script settings before running it.
- Start with a small scrape when possible.
- Respect website terms, `robots.txt`, and rate limits.
- Never commit generated data, cookies, passwords, or API keys.
- Website APIs and selectors can change.

## Upload to GitHub

```powershell
git init
git add .
git commit -m "Add scraping scripts"
git branch -M main
git remote add origin https://github.com/YOUR_NAME/YOUR_REPOSITORY.git
git push -u origin main
```

## License

This project is licensed under the [MIT License](LICENSE).
