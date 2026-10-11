# MyGarage-dataset

A sample data repo for [MyGarage-webapp](https://github.com/jt87/MyGarage-webapp). Copy this layout to keep track of your own tools, manuals, consumables and projects, then point your MyGarage server at your copy.

Everything here is made up. The "Acme" tools don't exist, and the PDFs and photos are placeholders. Replace them with your own.

## Getting started

1. On GitHub, use this repo as a template (or fork it) to make your own data repo. Make it **private** if it will hold receipts and serial numbers.
2. Delete the sample folders in `tools/` and `projects/`, and the sample rows in the inventory table below.
3. Add your tools and projects as described below.
4. Deploy [MyGarage-webapp](https://github.com/jt87/MyGarage-webapp) with `GIT_REPO_URL` set to your new repo.

## Layout

```
tools/        One folder per tool: manual PDF + a README with the details
projects/     One folder per project: plans, cut lists, photos, notes
reference/    General shop info that isn't tied to one tool (see reference/consumables.md for one shopping list)
_templates/   Copy these to start a new tool or project
CLAUDE.md     The conventions, written as standing rules for Claude Code (useful for people, too)
```

## Adding a tool

1. Copy `_templates/tool/` to `tools/<brand>-<model>/` (lowercase, dashes, e.g. `tools/acme-ts10/`).
2. Drop the manual in as `manual.pdf` (extra docs: `parts-list.pdf`, `quick-start.pdf`, etc.), photos as `photo.jpg` (more as `photo-*.jpg`, and `nameplate.jpg` for the label), and the receipt as `receipt.pdf` or `receipt.jpg`.
3. Fill in what you know in `README.md`. Blanks are fine.
4. Add a row to the inventory table below, including the price paid and replacement value.

## Starting a project

Copy `_templates/project/` to `projects/YYYY-MM-<short-name>/` (e.g. `projects/2027-01-bookshelf/`).

## What the web app reads

Keep these formats and the app shows everything; anything else in a README shows up as written.

| Where | What it reads |
|-------|---------------|
| This `README.md` | The table under `## Inventory` (Tool, Category, Paid, Replacement value, Folder), the **Total** row, and the "Values last refreshed" line |
| Tool `README.md` | The `# Brand Model — Name` title, the two-column spec table (including `Purchased` and `Replacement value`), and the `## Consumables & parts` and `## Maintenance log` tables |
| Consumables table | Four columns. **Bold** part numbers become store searches; stores named in "Where to buy" get their own buttons |
| Tool folder files | Images are the photo gallery (`photo.jpg` first, nameplates last); PDFs named `manual` or `guide` are manuals; other PDFs are documents; names containing `receipt`, `invoice`, `proof`, `order` or `bill-of-sale` are proof of purchase |
| Project `README.md` | The `Status:`, `Started:` and `Finished:` lines, `## Goal`, and links to `../../tools/<folder>/` (these list the project on the tool's page). STL files open in a 3D viewer |
| `reference/` | Every `.md` file becomes a page |

## Inventory

Replacement values are the **MSRP** (list price, not sale price) of comparable new tools, for insurance. Refresh them every quarter (see `CLAUDE.md`).

Values last refreshed: January 2027

| Tool | Category | Paid | Replacement value | Folder |
|------|----------|------|-------------------|--------|
| Acme TS10 10" jobsite table saw | Table saw | $150 (used) | ~$330 | [tools/acme-ts10](tools/acme-ts10/) |
| Acme DD20 20V drill/driver | Drill | $99 + tax | ~$129 | [tools/acme-dd20](tools/acme-dd20/) |
| **Total** | | | **~$459** (as of Jan 2027) | |
