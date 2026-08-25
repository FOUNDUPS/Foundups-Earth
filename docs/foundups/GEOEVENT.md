# GeoEvent contract

`GeoEvent` is the portable observation envelope shared by AutoPost, GeoSync, FoundUps Earth, and participating FoundUps.

## Minimal envelope

```json
{
  "schemaVersion": "0.1.0",
  "eventId": "content-addressed-or-uuid",
  "eventType": "observation",
  "subjectType": "environmental_condition",
  "capturedAt": "RFC3339 timestamp",
  "receivedAt": "RFC3339 timestamp",
  "geometry": {
    "type": "Point",
    "coordinates": [0, 0],
    "accuracyM": 0,
    "bearingDeg": 0
  },
  "evidence": [],
  "claims": [],
  "provenance": {
    "producerType": "autopost",
    "producerId": "pseudonymous identifier",
    "signature": "detached signature reference"
  },
  "privacy": {
    "classification": "public",
    "redactions": [],
    "locationPrecision": "exact"
  },
  "status": "submitted"
}
```

## Evidence entries

Evidence may reference video, audio, still frames, depth, motion, orientation, transcript, sensor readings, public-feed records, derived embeddings, or human attestations. Large media stays in content-addressed object storage; the event contains hashes, access policy, capture metadata, and derivation relationships.

AI-generated claims must identify their model/provider, prompt-policy version, confidence, input evidence, and whether processing occurred locally or remotely. Derived claims never replace original evidence.

## Lifecycle

`draft -> submitted -> quarantined|accepted -> unverified -> corroborated|verified|disputed -> resolved|superseded`

Ingestion state and verification state are separate. A technically valid upload can remain unverified. A disputed event remains visible only where policy permits and must not be relabeled as false without a recorded decision.

## Change and outcomes

Events relate through explicit edges:

- `duplicates`
- `corroborates`
- `contradicts`
- `observes_same_condition`
- `caused_by`
- `responds_to`
- `work_receipt_for`
- `outcome_of`
- `supersedes`

This permits before/after evaluation without mutating historical evidence.
