# National Ride API — V0.2

Professionalized backend foundation for a Romanian ride-hailing / transport-alternative platform.

## Improvements in V0.2
- Versioned REST endpoints under `/api/v1`
- Helmet security headers, CORS, request logging and environment configuration
- Centralized validation and error handling
- Domain validation and duplicate checks
- Fare quotes expire after 5 minutes and rides reference immutable quotes
- Explicit ride state machine prevents invalid transitions
- GPS points are accepted only during trackable ride states
- Financial ledger entry is created on ride completion
- Audit trail for important mutations
- Consistent `{ data: ... }` / `{ error: ... }` API envelopes

## Run
```bash
cp .env.example .env
npm install
npm run check
npm start
```

Then open `http://localhost:3000/health`.

## Important production work
This V0.2 intentionally keeps an in-memory repository so the domain/API can be tested quickly. Before production or ADR audit, replace it with PostgreSQL + migrations, add authentication/authorization, payment provider integration, encrypted document storage, rate limiting, observability, backups, retention policies, GDPR workflows, electronic archiving and automated tests.
