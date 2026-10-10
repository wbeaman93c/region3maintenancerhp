# Region 3 Fleet Maintenance — New Build

This is a new, independent website. No login is included.

## Start locally
Requires Node.js 18 or newer. Run `npm start`, then visit `http://localhost:3000`.

## Deploy to Railway
1. Create a NEW GitHub repository and upload `server.js`, `package.json`, and the entire `public` folder.
2. Create a new Railway service from the GitHub repository. Railway will run `npm start`.
3. **Before entering real data**, attach a Railway persistent volume mounted at `/app/data` and set environment variable `DATA_DIR=/app/data`. Without persistent storage, saved reports can disappear when Railway redeploys.
4. Generate a Railway domain and test the website. Point your custom domain to the service only when ready.

## What it does
- Dashboard for units 8300–8323, due-soon PM (within 500 miles), overdue PM and out-of-service units.
- Fleet Maintenance: comprehensive basic PM inspection, work completed, deficiencies, notes, and disposition.
- Maintenance Records: saved report history, filter by unit, view and print.
- Completing **Full scheduled PM completed** resets the next PM to current mileage + 5,000 miles. A standalone oil change or tire rotation does NOT reset the full PM interval.
- Optional estimated weekly mileage per truck gives a projected next PM date. The date is an estimate, not a guarantee.
- Mileage and reports persist in a JSON data file on the server, provided DATA_DIR points to persistent storage.

## Operational notes
- No login means anyone with access to the website URL can view or submit records. Restrict network access if needed.
- Records cannot be edited or deleted in the UI; this protects submitted history. Export/backup and admin tools can be added later.
- This is a basic operational PM checklist, not a substitute for manufacturer-specific service requirements, qualified mechanical inspection, or applicable regulatory inspections.
