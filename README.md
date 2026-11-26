# FROST_Dashboard

Program dashboard for all data and control system around product development.

This is the FROST Aura Program Hub: the internal operating hub for FROST Active / Crowdiego Labs: program, ideation, field testing, manufacturing, purchasing, sales, marketing, funding and finance in one page.

## What's here

| Path | What it is |
|---|---|
| `index.html` | The hub itself: a single self-contained page (HTML, CSS and JavaScript). |
| `src/` | The source of each module as it was added (field testing, funding, sales and POs, ideate, Jarvis, build planner, marketing, timesheet, sign-in, strategy, development, costing). These are already inlined in `index.html`; they're kept for reading and diffs. |
| `data/hub-export-YYYY-MM-DD.json` | A snapshot of the hub's database from **Export all**. |

## Running it

The hub is published as a Claude artifact and uses Claude's artifact runtime (`window.claude`) for its database, sign-in, Jarvis and downloads. Opened directly from this repo in a browser, it loads but runs without a database (nothing is saved).

Live hub: open it from claude.ai (owner access).

## Data snapshots

1. In the hub, click **Export all** (top right). It downloads `frost-aura-hub-YYYY-MM-DD.json` with every collection, settings and the manufacturing data.
2. Save it into `data/` and commit.

Timesheets and the activity log are personal data about team members. Keep them in `data/private/` (ignored by git) unless this repository is private and you intend to store them.

## Security notes

- Keep this repository **private**. It contains customer leads, investors, vendors, prices and team contacts.
- No passwords or API keys are stored in the hub. The shared sign-in password is checked against a salted hash in `index.html`; it's a convenience gate, not real security, and anyone who reads the code can test guesses against it. Real access control comes from who the artifact is shared with on claude.ai and the database rules.
