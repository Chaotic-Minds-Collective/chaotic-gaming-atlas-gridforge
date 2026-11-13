# CMG GridForge — Implementation Plan

## Purpose
Configuration authoring and validation workbench for ATLAS clusters, grids and resource coverage.

## Feature scope
- Server-grid JSON authoring, schema validation and diff
- Grid topology editor and transfer routes
- Visual map editor for islands, regions, resources and creatures
- Resource/creature coverage and missing-reference reports
- Grid/server connection and port checks
- Import/export, drafts, backups and bundles

## Dependencies
- ChaoticAtlasResourceMap after provenance/license audit
- Core server registry and scoped project permissions
- ATLAS config contract; World consumes validated data
- Review existing chaotic-atlas-admin frontend/backend

## Data ownership
GridForge owns drafts, map layers, catalogues, validation reports, schema versions and generated JSON. Core owns identity/roles/server registry. Preserve asset source/license metadata.

## Milestones
1. Obtain real versioned grid JSON and authoritative schema
2. Audit resource-map provenance and licensing
3. Build parser, validator and round-trip tests
4. Build visual map/topology editor
5. Add resource/creature coverage checks
6. Add export, diff, backup and staged apply

## Technical gates and risks
- Never guess grid JSON schema
- Do not redistribute unverified assets
- Distinguish static validation from in-game validation

## Shared engineering requirements
- Use authenticated, least-privilege Core APIs; no direct database credentials in plugins.
- Preserve provider identifiers as strings; display names are not identifiers.
- Carry cluster, grid and server context on applicable records/events.
- Use stable event IDs, idempotency keys and correlation IDs.
- Keep network work off game-critical threads; use bounded timeouts, retries and circuit breakers.
- Keep secrets out of source control and separate credentials per server/integration.
- Add unit tests, fake-adapter contract tests and isolated runtime compatibility tests.
- Gate unsupported features behind explicit capabilities; fail closed for privileged actions.
- Do not deploy to production or change live server configuration during repository planning.

## Current readiness
Documentation and planning scaffold. Exact ATLAS server build, loader, SDK, callbacks and feature-specific capabilities require isolated reproducible validation.
