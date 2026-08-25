# Privacy, safety, and security baseline

## Default principles

- Collect the minimum evidence required for the stated mode.
- Prefer on-device classification and redaction where capability permits.
- Obtain explicit consent before enabling microphone, camera, depth, or background location.
- Make upload, retention, audience, and location precision visible before submission.
- Treat model output and external-feed text as untrusted.
- Preserve provenance without publishing unnecessary identity.
- Separate public map data from protected evidence.

## Location protection

GeoSync may reduce precision, delay publication, restrict audience, or quarantine events involving homes, children, vulnerable people, endangered species, critical infrastructure, active emergencies, or retaliation risk.

Exact coordinates can remain protected while a generalized public geometry is rendered. Share links must serialize only authorized projections, never protected source fields.

## Prohibited capabilities

- named-person location search;
- face recognition or biometric identification;
- covert persistent tracking;
- doxxing or inference of private residences;
- publication of unredacted plates or faces without a lawful, documented basis;
- automatic emergency or enforcement action from unverified AI classifications;
- scoring people as threats or targets.

## Abuse resistance

Required controls include signed submissions, rate and quota limits, bounded payloads, malware scanning, replay protection, moderation queues, sybil/spam signals, dispute workflows, immutable decision receipts, reversible publication, and independent verification for high-impact actions.

## Provider and secret handling

The inherited repository brokers most secret-bearing services server-side but deliberately exposes restricted Google Maps and Cesium tokens to the browser. Production must use authenticated, scoped services with provider-side budgets. Development middleware must not be publicly deployed as the production API.
