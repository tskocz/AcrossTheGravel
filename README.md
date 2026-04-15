# AcrossTheGravel Roadmap

## Planning principles

- Deliver a narrow personal MVP first.
- Preserve a clean path to a small multi-user deployment later.
- Prioritize correctness of geography and completion logic over breadth of features.
- Keep the repo and workflow AI-friendly from the beginning.

## Phase 0: Foundation

Goal: make the repo and development workflow usable.

- Create monorepo structure
- Add starter docs and AI guidance
- Add basic lint/test/CI skeleton
- Set up local Postgres/PostGIS development environment
- Create initial issue tracker and milestone plan

Exit criteria:

- Repo can be cloned and understood quickly
- Basic local development steps are documented
- AI agents have enough context to make safe, small changes

## Phase 1: Personal proof of concept

Goal: prove the core ingestion and map display loop.

- Upload GPX and FIT files
- Parse and normalize activity data
- Import a limited OSM geography slice
- Match activities to a first-pass road/trail model
- Render completed and remaining segments on a map

Exit criteria:

- A single user can upload files and see useful completion output
- Core data flow works end to end on local or low-cost hosting

## Phase 2: Personal MVP

Goal: make AcrossTheGravel trustworthy enough for repeated personal use.

- Improve matching quality and edge-case handling
- Add configurable completion rules
- Add progress summaries and filtering
- Add data correction and rerun workflows
- Improve observability, error handling, and backup plan

Exit criteria:

- Results are stable enough to use regularly
- Reprocessing and troubleshooting are practical

## Phase 3: Friends-and-family readiness

Goal: support a small trusted user group.

- Add simple auth and user isolation
- Add basic admin and support workflows
- Harden CI, deployment, and rollback steps
- Review privacy, retention, and security assumptions

Exit criteria:

- Multiple trusted users can use the system safely
- Operational risk is reasonable for a small private deployment

## Phase 4: Expansion

Goal: broaden inputs and geography coverage.

- Add Strava import
- Add Garmin and Apple Fitness later
- Expand beyond OSM roads/trails to other layer types
- Add richer completion modes and geography types

Exit criteria:

- New integrations and data layers fit without major redesign

## Current open decisions to resolve early

- Completion rule set
- OSM path and surface inclusion rules
- Geography hierarchy and identifiers
- Deployment target and cost ceiling
