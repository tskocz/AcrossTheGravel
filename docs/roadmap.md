# AcrossTheGravel Product

## Summary

AcrossTheGravel is a map-based app that helps a user understand what they have completed within a geography by comparing uploaded activity tracks against a known network of roads, trails, or other geographic features.

## Problem statement

Activity files contain a lot of useful location data, but they do not by themselves answer questions like "What roads have I covered?", "What trails are left?", or "How complete am I within this area?" AcrossTheGravel should turn raw activity tracks into clear, visual progress.

## Initial user

- Primary user: the project owner
- Near-term expansion: trusted friends and family

## MVP scope

The first usable version should:

- Accept GPX and FIT uploads
- Ingest and normalize activity data
- Use OSM as the first geographic source
- Focus on roads and trails before adding other feature types
- Compute completion using configurable rules
- Display completed and remaining coverage on a map
- Provide basic progress metrics for a selected geography

## Non-goals for the first version

- Public social features
- Large-scale multi-tenant architecture
- Native mobile apps
- External integrations before file upload works well
- Broad support for every geographic feature class

## Future directions

- Strava import after file upload is solid
- Garmin and Apple Fitness after Strava
- Additional layers such as peaks, national parks, county, state, or federal feature sets
- More advanced completion modes and filters
- Friends-and-family sharing and lightweight collaboration

## Product principles

- Start narrow and make the result trustworthy.
- Prefer understandable progress rules over clever but opaque scoring.
- Let map-based review explain how completion was determined.
- Keep user control over what counts toward completion.

## Open questions

- Which OSM path and surface types should count in the MVP?
- What is the minimum geography model for launch?
- How much manual correction is needed when matching tracks to mapped features?
- What should happen when data sources conflict or are incomplete?
