# Cursor AI Rules for this project

## ⚠️ DEPLOYMENTS — ALWAYS ASK FIRST

**Never run `netlify deploy --prod` without explicit user confirmation.**

Netlify production deploys consume build credits. Always stop and ask:
> "Ready to deploy to prod?" and wait for a "yes" before running the command.

Draft deploys (`netlify deploy` without `--prod`) are also worth asking about but are lower stakes.

## Git pushes
Pushing to GitHub (`git push`) is fine to do as part of a commit workflow, but confirm before combining a push + prod deploy in a single command.

## Project overview
- Static single-page site: `index.html`
- Netlify Edge Functions: `netlify/edge-functions/`
  - `schedule.js` → `/schedule` — fetches meet schedule from Google Sheets API
  - `sheet-data.js` → `/sheet-data?tab=<tabname>` — generic JSON endpoint for any sheet tab
- Netlify env vars required: `GOOGLE_SHEETS_ID`, `GOOGLE_SHEETS_API_KEY`
