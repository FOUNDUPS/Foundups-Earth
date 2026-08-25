# Platform architecture

## Repository role

FoundUps Earth is an ecosystem platform, not one FoundUp. Executable FoundUps use it through contracts rather than copying its map stack.

| Component | Responsibility |
|---|---|
| AutoPost | Capture and interaction client; produces evidence-bearing observations and receives spatial experiences |
| GeoSync | Ingestion, normalization, deduplication, synchronization, geospatial clustering, and privacy policy enforcement |
| 3V engine | Verification, validation, and valuation decisions with receipts |
| FoundUps Earth | Spatial read model, visualization, temporal comparison, and activation surface |
| RedDog | Intent-preserving interface that proposes routes, skills, work, or FoundUp launches |
| Foundups-Agent | Canonical contracts, WSP governance, orchestration, worker authorization, and registry |
| Domain FoundUp | Performs bounded work and emits evidence and outcome receipts |

## Event flow

```text
AutoPost / sensor / public feed
            |
            v
         GeoEvent
            |
            v
         GeoSync ---- privacy/redaction/quarantine
            |
            v
       3V assessment
            |
            v
    FoundUps Earth read model
            |
            +---- existing FoundUp
            |
            +---- RedDog launch proposal
            |
            v
       work + receipts
            |
            v
      outcome observation
```

## Required separation

The visualization must never become the authoritative ledger. It is a projection derived from signed events and decisions. Removing or changing a marker does not rewrite source evidence.

AutoPost must not write directly into verified map state. It submits evidence. GeoSync assigns ingestion status; the 3V engine assigns epistemic status; FoundUps Earth renders both honestly.

## Layer contract

Every spatial layer must expose:

- stable layer and provider identifiers;
- declared entity and event types;
- bounding-box and time-window queries;
- source attribution and applicable terms;
- freshness, latency, and expiry policies;
- `LIVE`, `DELAYED`, `RECONSTRUCTED`, `SIMULATED`, `UNAVAILABLE`, or `DISPUTED` state;
- privacy classification;
- failure behavior without silent fallback;
- resource and quota costs;
- serialization rules for shareable views.

## Provider neutrality

CesiumJS is the initial renderer, not a constitutional dependency. OpenAI Realtime is an optional adapter, not the reasoning authority. Map, model, voice, storage, and data providers must sit behind capabilities so FoundUps orchestration can select them without hardcoded product assumptions.

## Deployment boundary

The inherited Vite middleware is suitable for local exploration only. Production extraction requires separate services for:

- public web/PWA assets;
- authenticated API gateway;
- GeoSync ingestion;
- evidence/object storage;
- spatial database and read models;
- provider adapters and quota governance;
- authorization and moderation;
- append-only receipts and audit trails.
