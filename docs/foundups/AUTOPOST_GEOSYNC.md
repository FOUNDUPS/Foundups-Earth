# AutoPost and GeoSync

## AutoPost

AutoPost is the context-sensitive capture and interaction client. Its runtime mode may be selected by the user, RedDog, or a consented FoundUp skill.

Initial modes:

- observe: capture a condition or opportunity;
- document: create a durable media/provenance record;
- contribute: complete a FoundUp mission and emit a receipt;
- discover: find nearby FoundUps, events, resources, or experiences;
- play: enter a spatial game or AR experience;
- verify: recapture or attest to an existing GeoEvent;

Modes control the UI and requested sensors but do not alter the underlying evidence rules.

## GeoSync

GeoSync is the spatial synchronization and reconciliation layer. It:

- validates envelopes and signatures;
- applies consent, redaction, and location-precision policy;
- strips unnecessary device identifiers;
- stores media by content hash;
- detects duplicates and coordinated spam;
- groups related events across space and time;
- synchronizes offline submissions when connectivity returns;
- routes claims for 3V assessment;
- publishes authorized projections to FoundUps Earth;
- sends missions and relevant changes back to AutoPost.

## Bidirectional relationship

AutoPost does not merely improve FoundUps Earth by uploading observations. FoundUps Earth improves AutoPost by returning better spatial context, verified missions, known conditions, active FoundUps, and experience manifests.

```text
AutoPost evidence  ---> GeoSync ---> FoundUps Earth
AutoPost experience <--- GeoSync <--- missions/context
```

## Offline-first requirement

AutoPost must be able to capture, hash, redact, and queue a GeoEvent without network access. Synchronization is explicit, resumable, idempotent, and observable. There is no silent cloud fallback for private media or local AI processing.
