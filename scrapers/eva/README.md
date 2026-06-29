# Eva scraper

## Files

- scraper.js - the final scraper
- sample_data.csv - 10 cleaned example products
- README.md - usage and cleanup notes

## What happened

The workspace contained production scripts, older versions, tests, debug tools, helpers, and generated datasets. This folder keeps only the clearest final scraping script. Everything else was excluded from this GitHub copy to make the project easier to understand.

The original workspace files were not changed.

## Requirements

Node.js 20+ is required. Install the shared dependencies from the repository root before running this script.

## Run

    node scraper.js

The scraper controls its own output names and request settings. Review the constants near the beginning of the script before running a large scrape.

## Important

- Check the website terms and robots policy.
- Start with a small run when a limit option is available.
- Keep request delays enabled.
- Never commit outputs, cookies, credentials, or browser profiles.
- Website APIs and selectors can change over time.


