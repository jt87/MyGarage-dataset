# Garage repo: standing rules

## Replacement values (for insurance)

Every tool's replacement value must be refreshed once a quarter (January, April, July, October).

To refresh:
1. For each folder in `tools/`, look up the **MSRP** (manufacturer's suggested retail / list / regular price) of a comparable **new** tool. Use the same comparable models listed in its README if they're still sold; otherwise pick the closest current equivalent.
   - **Never use a sale, clearance, coupon, member, open-box, used or bundle price.** If a page shows both a "was" and a "now" price, use the "was"/list price.
   - Prefer the manufacturer's own site. If it shows no price, use the regular (non-sale) price at a major retailer (Home Depot, Lowe's, Amazon, etc.) and say where it came from.
   - Note in the README that the value is the MSRP, plus its source and date.
2. Update the "Replacement value" row in that tool's README with the new value, the month and year, and the comparable models and prices.
3. Update the Replacement value column and the **Total** row in the main `README.md` inventory table, plus the "Values last refreshed" line above it.
4. Commit with a message like `Quarterly replacement value refresh (2027 Q1)` and push to `main`.

When adding a new tool, set its replacement value at the same time.

## Conventions

Tool folders are `tools/<brand>-<model>/` and contain `manual.pdf` and a `README.md` copied from `_templates/tool/`. Name proof of purchase files `receipt.pdf` / `receipt-YYYY-MM-DD.jpg` (any name containing `receipt` or `invoice` works). Project folders are `projects/YYYY-MM-<short-name>/`. Keep the inventory table in `README.md` in sync with `tools/`.

## Web app

This repo is displayed by [MyGarage-webapp](https://github.com/jt87/MyGarage-webapp), which parses the README formats above, so keep them: the `# Brand Model — Name` title, the two-column spec table with `Purchased` and `Replacement value` rows, the four-column `## Consumables & parts` table with part numbers in **bold**, the `## Maintenance log` table, and the inventory table in `README.md`. To preview changes, run the web app locally with `REPO_PATH` pointing at this repo (see its README).
