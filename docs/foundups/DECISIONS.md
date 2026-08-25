# Architecture decisions

## ADR-001: FoundUps Earth is a platform

**Decision:** FoundUps Earth is an ecosystem spatial platform, not GotJunk, FoundUps House, or another individual FoundUp.

**Reason:** Multiple independent FoundUps need the same spatial evidence, manifestation, temporal comparison, and activation capabilities.

## ADR-002: AutoPost is bidirectional

**Decision:** AutoPost is both an evidence producer and an experience client.

**Reason:** The same phone surface may document pollution, verify work, discover a FoundUp, or enter a spatial game. Capture mechanics must not constrain the platform's purpose.

## ADR-003: GeoSync owns reconciliation

**Decision:** AutoPost cannot directly mutate verified map state.

**Reason:** Deduplication, privacy policy, disputes, provenance, and 3V decisions require an explicit trust boundary.

## ADR-004: Visualization is a projection

**Decision:** FoundUps Earth renders authorized read models derived from events and receipts.

**Reason:** The map must not become an unauditable ledger or permit UI state to rewrite evidence.

## ADR-005: Defer interaction commitment

**Decision:** AR, tapping, scanning, voice, wearables, and game mechanics remain replaceable clients over shared contracts.

**Reason:** The idea is valuable, but selecting mechanics now would prematurely constrain future devices and experiences.

## ADR-006: Preserve upstream, extract deliberately

**Decision:** Maintain the upstream relationship while incrementally extracting a FoundUps spatial kernel.

**Reason:** A wholesale rename would conceal licensing, data, security, monolith, and provider-coupling risks.

## ADR-007: Release gates run in repository CI

**Decision:** Clean install, production dependency audit, unit tests, production build, and browser tracking regression are required before changes enter `main`.

**Reason:** Spatial rendering behavior requires a reproducible browser environment in addition to static and unit verification.
