# Region 3 PM Website — New iPad-friendly build

Fresh Node.js website with no external npm dependencies and no login.

## Start locally
`npm start` then open http://localhost:3000

## Railway
Deploy this folder/repository as a Node.js service (start command `npm start`). Add a Railway Volume mounted at `/app/data` and set environment variable `DATA_DIR=/app/data`. Records are stored in `records.json` on the volume. Set up periodic external backups using the Dashboard's Export Backup button. A Railway volume is persistent storage, not a managed database or automatic backup.

## Features
- Dashboard for units 8300–8323, 5,000-mile PM schedule, 500-mile warning, next PM due mileage based on last completed scheduled PM + 5,000 miles.
- Tablet-friendly step-by-step inspection with autosaved local draft, per-item ratings and comments.
- Tire PSI and tread depth (32nds) for four positions plus spare.
- Separate service actions and full scheduled PM flag; only a full scheduled PM resets next PM interval.
- Stored inspection records, printable details, JSON backup export.

## Important
- No authentication: anyone with the site URL can view, edit and submit reports. Restrict access at network/platform level if needed.
- Browser draft autosave is device-local, while submitted reports are stored server-side.
- Single-instance JSON storage is intended for a small team and should not be used with multiple Railway replicas. For multi-instance use, migrate to PostgreSQL.
- This is an operational inspection form, not a substitute for OEM maintenance instructions, qualified mechanic judgment, or legally required inspections.


THEME UPDATE: Tennessee Rural Service Patrol branding, provided official seal, one Keeping Tennessee Moving slogan in the header, redesigned responsive dashboard, original PM and records functionality retained. Dashboard values come from actual stored data; no mock mileage is seeded.
