# TPG HQ

Business blueprints, journey maps, contacts, equipment, tasks, processes, procedures, documents and training.

## Source snapshot

Initial source-only export of the local development workspace on 2026-10-28. This is not a production release or a claim that the complete exported working tree has passed a fresh acceptance run. Local Git history, internal governance/evidence records, databases, uploaded documents, backups, credentials, installed dependencies and compiled runtime artifacts are excluded.

## Local development

Use Node.js 24.18.0, npm 11.16.0 and PostgreSQL 18. Start with `npm ci --ignore-scripts --no-audit --no-fund`, provide a dedicated local non-production `DATABASE_URL`, and run `npm run db:generate`. Build the API using `npx nx run api:build` and the web app using `npx nx run web:build`.

The existing [local handoff](BROWSER_UAT_V0_0_HANDOFF.md) and [API operations guide](apps/api/FOUNDATION_OPERATIONS.md) describe configuration, migrations and synthetic provisioning. These are historical guides: their feature descriptions and migration counts may lag this snapshot. Apply all checked-in migrations to a fresh dedicated database. Never run reset or seed commands against business or production data.

Keep `BOS_ENVIRONMENT_ID=UAT` and bind services to localhost. No live business data or user credentials are supplied. The repository being public does not authorize public hosting of the application or production use.

## Checks and limitations

Package scripts include lint, unit tests, API/browser tests and security scans. Some historical evidence scripts reference internal files not included in this export; those evidence checks are not a portable release certification. The secret-scan helper currently targets macOS ARM64.

Third-party dependencies are obtained separately through npm and retain their respective licenses. Existing legal publication files are retained because the application verifies their exact hashes. Public source visibility does not change those application access terms or grant rights to third-party branding.
