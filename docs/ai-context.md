# AcrossTheGravel Architecture

## Purpose

This document describes the starter system design for AcrossTheGravel, a personal-first proof of concept that may later support a small friends-and-family audience.

## High-level architecture

- `apps/web`: Next.js + TypeScript frontend for map views, upload flow, and progress reporting
- `apps/api`: FastAPI application for upload handling, query APIs, auth later, and administrative endpoints
- `jobs/`: background processes for import, normalization, map matching, and recomputation
- `db/`: PostgreSQL + PostGIS schema, migrations, and seed/reference data
- `docs/`: product, architecture, roadmap, and AI guidance

## Main data flow

1. User uploads GPX or FIT activity data.
2. Backend validates the file and stores the raw upload and normalized metadata.
3. Background jobs parse the activity into track points and derived geometry.
4. Geography reference data from OSM is loaded into PostGIS.
5. Matching logic links activity geometry to roads, trails, or other tracked features.
6. Completion logic calculates covered, uncovered, and partially covered features.
7. API serves progress summaries and map-ready geometry to the frontend.
8. Frontend renders coverage and remaining work using MapLibre GL JS.

## Early design choices

- Keep the first version as a monorepo.
- Keep geographic computation close to PostGIS where practical.
- Use asynchronous jobs for heavy ingest and recomputation.
- Store the durable product and architecture context in the repo so AI agents can work from versioned source material.

## Suggested repository layout

```text
.github/
  workflows/
  copilot-instructions.md
docs/
apps/
  web/
  api/
jobs/
db/
  migrations/
  seeds/
scripts/
```

## Boundaries and responsibilities

### Frontend

- Upload UX
- Map display
- Progress dashboards and drill-down views
- Minimal client-side business logic

### API

- Validation and persistence of uploads
- Read APIs for progress, geography, and activity history
- Triggering background work
- Auth and permissions when the project expands beyond single-user use

### Jobs

- File parsing
- Geometry normalization
- Geography import and refresh
- Matching and completion recomputation

### Database

- Activity metadata and derived geometry
- Geography reference data
- Completion state and summary tables
- Audit-friendly timestamps and ownership fields where appropriate

## Security and operational notes

- Do not store secrets in the repo.
- Minimize retained raw personal location data unless it is required for product value.
- Assume future users may require stronger separation of data, even if the first version is single-user.
- Keep import and matching steps observable with logs and retry-safe job design.

## Known TBD items

- Auth approach for friends-and-family use
- Exact storage strategy for raw uploads
- Map matching approach and tolerance rules
- Hosting model and background job runtime
