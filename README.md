# OHC Max Puissance Tournament Dashboard

A live, mobile friendly dashboard for OHC Max Puissance in the 2012 D3 Contact division. Pulls directly from the official tournament Google Sheets every 5 minutes (and every time you open the page).

## Live site

https://brentmartel.github.io/ohc-tournament-dashboard/

## How it works

The page is a single `index.html` file. When it loads, it fetches two Google Sheets as CSV using the `gviz/tq?tqx=out:csv` endpoint:

- Schedule: https://docs.google.com/spreadsheets/d/11sEDdz4JWg7VlMuLyMWP7hfJXzsjHkscNjvYRJOR-Mo
- Standings: https://docs.google.com/spreadsheets/d/1g4u13-1nB3M1cInWDzsuJ1kV2FOZj27XwiEYA-D0haI

Both sheets must be set to "Anyone with the link can view" for the fetch to work.

The page auto refreshes every 5 minutes while open, and also on window focus. There is a manual Refresh button in the header.

## Updating the tournament

When it is time for a new tournament weekend, edit the `SCHEDULE_SHEET_ID` and `STANDINGS_SHEET_ID` constants near the top of the inline script in `index.html` and commit. GitHub Pages will redeploy automatically.

## Tech

- Single static HTML file, no build step
- React 18 and Babel Standalone from unpkg
- PapaParse for CSV parsing
- Hosted on GitHub Pages
