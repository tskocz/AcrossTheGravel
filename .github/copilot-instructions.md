# Copilot Instructions

You are working in the AcrossTheGravel monorepo for a personal-first map-based activity completion app.

## Product and architecture context

- Backend and jobs: Python + FastAPI
- Database: PostgreSQL + PostGIS
- Frontend: Next.js + TypeScript
- Map rendering: MapLibre GL JS
- Initial input: GPX and FIT uploads
- Initial geography source: OpenStreetMap
- Initial tracked features: roads and trails
- The first goal is a proof of concept that can later grow to a small friends-and-family deployment.

## General rules

- Prefer simple, boring, maintainable solutions.
- Keep changes small and tightly scoped.
- Do not introduce major new libraries without a clear reason.
- Do not invent product policy when requirements are still open; surface the assumption instead.
- Update nearby docs when changing behavior, architecture, or developer workflow.

## Backend guidance

- Keep request handlers thin.
- Put heavy parsing, matching, and recomputation work in jobs or service layers.
- Validate all external input.
- Make geospatial logic explicit and testable.
- Avoid hidden side effects.

## Frontend guidance

- Use TypeScript strictly.
- Keep map rendering concerns separate from product logic.
- Prefer readable UI flows over clever abstractions.
- Avoid overbuilding for multi-user or public use until needed.

## Database and data guidance

- PostgreSQL + PostGIS is the source of truth for core product data.
- Design schemas for traceability of uploads, derived geometry, and completion results.
- Keep migrations clear and reversible where practical.
- Do not add sample personal location data to the repo.

## Testing and quality

- Add or update tests for meaningful behavior changes.
- Keep linting and type checking green.
- When behavior is uncertain, prefer TODO notes and small seams over fake certainty.

## Security and privacy

- Never commit secrets.
- Treat uploaded files as untrusted.
- Minimize retention and exposure of raw location data.
- Favor least-privilege and safe defaults.

## Output expectations

When suggesting or generating changes:

- State assumptions briefly.
- Mention which files should change.
- Prefer incremental PR-sized work.
- Call out follow-up tasks when a change should be split.
