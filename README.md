# CMG ATLAS GridForge Plugin

Configuration authoring and validation workbench for ATLAS clusters, grids and resource coverage.

This Chaotic Minds Gaming (CMG)-specific plugin extends [CMG Core](https://github.com/Chaotic-Minds-Collective/chaotic-minds-gaming-atlas-core) and the [ATLAS integration adapter](https://github.com/Chaotic-Minds-Collective/chaotic-minds-gaming-atlas); it does not replace either foundation.

## Feature scope
- Server-grid JSON authoring, schema validation and diff
- Grid topology editor and transfer routes
- Visual map editor for islands, regions, resources and creatures
- Resource/creature coverage and missing-reference reports
- Grid/server connection and port checks
- Import/export, drafts, backups and bundles

## Architecture and dependencies
- CMG ATLAS Resource Map after provenance/license audit
- Core server registry and scoped project permissions
- ATLAS config contract; World consumes validated data
- Review existing cmg-atlas-admin-plugin frontend/backend

Core remains authoritative for shared identity, authorization and platform records. ATLAS-native calls pass through the shared adapter. This module owns its domain state and must not connect directly to PostgreSQL.

## Implementation plan
See [docs/IMPLEMENTATION_PLAN.md](docs/IMPLEMENTATION_PLAN.md) for data ownership, milestones and technical gates.

## Readiness
Planning scaffold only. Native ATLAS compatibility and feature-specific callbacks are not yet verified on an isolated server. No production deployment is implied.
