# Upstream adoption audit

Audited upstream: `bilawalsidhu/gods-eye-view`, public release commit `880a672` dated 2026-08-24.

## Decision

Adopt as a provenance-preserving technical fork and extraction source. Do not deploy the inherited application as the FoundUps production platform.

## Strengths

- CesiumJS photorealistic globe and mature camera behavior.
- Modular live spatial layers and entity tracking.
- Clear source/freshness states and visible attribution.
- Shareable spatial views, annotations, scene tools, and voice operations.
- Strong defensive attention to proxy destinations, response bounds, timeouts, redacted logging, quotas, and honest failure states.
- Extensive unit and visual QA surface.

## Material risks

- The upstream security document explicitly describes a local exploration/dev service, not a hardened production service.
- `vite.config.js` is also a roughly 7,383-line backend; `src/ui.js` exceeds 10,000 lines. Several layer modules exceed 3,000–5,000 lines, increasing extraction and regression risk.
- Voice and HUD code directly target OpenAI endpoints and named models, conflicting with FoundUps provider orchestration.
- No full PWA/offline capture/sync architecture is present.
- Code is MIT, but data and media are separately governed. OpenSky and Google News uses are noncommercial; TeleGeography bundled data is CC BY-NC-SA; Google/Cesium and other services impose proprietary terms.
- Required Google 3D tiles are metered and browser-visible through a restricted key.
- The public history is extremely young and effectively squashed, limiting independent maintenance evidence.
- No GitHub Actions workflow was present in the audited public state.

## Reuse classification

| Surface | Decision |
|---|---|
| Cesium rendering patterns | Extract/adapt |
| Camera and spatial annotation behavior | Extract/adapt |
| Layer freshness/provenance semantics | Preserve and generalize |
| Share-state patterns | Adapt with authorization filtering |
| Public-feed adapters | Optional; relicense and reapprove individually |
| Vite middleware backend | Replace for production |
| OpenAI Realtime integration | Convert to optional provider adapter |
| Military/spy presentation | Remove |
| Person-tracking prohibition | Preserve and strengthen |
| Upstream promotional media | Retain only in upstream reference; do not rebrand |

## Verification note

Static source, history, dependency declarations, tests, security documentation, known issues, and data terms were inspected. Dependency installation was attempted in the audit container but its package cache repeatedly failed with filesystem/tar extraction errors, so the upstream test suite was not independently certified by this audit. The fork must obtain reproducible clean-install, build, unit, and visual-QA evidence before implementation claims are accepted.
