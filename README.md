# FoundUps Earth

**The spatial manifestation layer for observations, FoundUps, work, and verified outcomes.**

FoundUps Earth transforms place-based evidence into coordinated action. AutoPost can document a condition, verify completed work, discover nearby FoundUps, or enter a future AR/game experience. GeoSync reconciles those interactions into privacy-aware spatial events. The 3V engine determines their verification, validation, and valuation state. FoundUps Earth renders the authorized result and connects needs to executable FoundUps.

```text
AutoPost / sensors / public feeds
                |
                v
             GeoSync
                |
                v
 Verification - Validation - Valuation
                |
                v
          FoundUps Earth
          /             \
 existing FoundUp    launch proposal
          \             /
           work + outcome
```

## Status

This repository is at **foundation/extraction stage**. It is a provenance-preserving derivative of [God's Eye View](https://github.com/bilawalsidhu/gods-eye-view), not yet a production FoundUps service.

The inherited runtime remains available for evaluation while the spatial kernel, GeoSync contracts, authorization model, and provider boundaries are extracted. Do not expose the inherited Vite development server as a public production backend.

## Platform boundaries

- **AutoPost** captures evidence and hosts context-sensitive spatial interactions.
- **GeoSync** ingests, redacts, deduplicates, clusters, synchronizes, and routes GeoEvents.
- **FoundUps Earth** visualizes authorized spatial state and FoundUp activity.
- **Foundups-Agent** owns WSP governance, orchestration, registries, and worker authorization.
- **GotJunk, FoundUps House, disaster recovery, environmental projects, and games** are consumers—not copies of the platform.

## FoundUps documentation

- [Vision](docs/foundups/VISION.md)
- [Architecture](docs/foundups/ARCHITECTURE.md)
- [GeoEvent contract](docs/foundups/GEOEVENT.md)
- [AutoPost and GeoSync](docs/foundups/AUTOPOST_GEOSYNC.md)
- [Privacy and security](docs/foundups/PRIVACY_SECURITY.md)
- [Roadmap](docs/foundups/ROADMAP.md)
- [Upstream adoption audit](docs/foundups/UPSTREAM_AUDIT.md)
- [Architecture decisions](docs/foundups/DECISIONS.md)
- [Attribution notice](NOTICE.md)
- [Original upstream README](UPSTREAM_README.md)

## Immediate proof of concept

The first complete vertical loop should be deliberately small:

1. AutoPost records an illegal dumping or polluted-site observation.
2. GeoSync creates and validates a `GeoEvent`.
3. FoundUps Earth displays its unverified state.
4. A second source corroborates it through the 3V path.
5. GotJunk accepts bounded cleanup work.
6. Worker receipts and a subsequent AutoPost capture demonstrate the outcome.
7. FoundUps Earth retains the before/after history and marks the condition resolved.

## Development

The inherited development runtime currently requires the upstream Node and provider configuration. Consult [UPSTREAM_README.md](UPSTREAM_README.md), [SECURITY.md](SECURITY.md), and [DATA_SOURCES.md](DATA_SOURCES.md) before running it.

```sh
npm install
npm test
npm run build
```

## Licensing

Source code is MIT-licensed subject to the notices in `LICENSE` and `NOTICE.md`. Third-party data, media, models, imagery, and services retain their own terms. Enabling a layer is a licensing and privacy decision, not merely a configuration choice.
