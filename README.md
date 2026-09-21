<!-- @scry.entry
id: design.rbay-design-team-overview~a54af379
kind: design
status: active
weight: 0.8
tags:
  - "topic:bay-definition"
  - "bay-definition"
  - "topic:design-team"
  - "design-team"
  - "rbay-design-team"
  - "scope:bay"
  - "bay"
summary: >
  Bay definition for @prmichaelsen/design-team — the 8-track design
  team family: architect, idealist, design-skeptic, scope-cutter,
  prior-art-researcher, red-team, requirements-analyst, spec-writer.
  Version 0.1.0. Includes bay.yaml, capabilities/tools.yaml,
  capabilities/permissions.yaml, principles.md (P1-P7 portability
  copy), and scry-sync CI workflow targeting the reflect-v2
  control-plane Worker. Status: all phases complete 2026-09-18;
  scry-sync e2e confirmed 2026-09-21; one open item is adding
  SYNC_API_KEY Actions secret to activate CI-driven marker push.
  Also: rbay-design-team, design-team bay, bay.yaml,
  @prmichaelsen/design-team, reflect-v2 bay, bay definition overview,
  design team track family, 8-track family.
rationale: >
  Orients any reader — human or agent — to the bay definition repo's
  current state, its 8 tracks, and the one pending activation step.
  Without this, the README would be stale (it was authored at Phase 0,
  before bay.yaml, capabilities/, and CI wiring existed).
applies: >
  orienting to the design-team bay definition, deploying the bay to a
  new reflect instance, reviewing bay status, checking which tracks
  are defined
seeded_questions:
  - "What tracks are in the design-team bay?"
  - "How do I deploy @prmichaelsen/design-team?"
  - "rbay-design-team overview"
  - "design team bay definition status"
@scry.entry.end -->

# rbay-design-team

Bay definition for the design-team track family:
`@prmichaelsen/design-team` v0.1.0.

## Tracks

| Track                | Role                                          |
|----------------------|-----------------------------------------------|
| architect            | System decomposition and spec structure       |
| spec-writer          | FR-style spec authoring                       |
| design-skeptic       | Premise challenger                            |
| idealist             | Quality and durability advocate               |
| scope-cutter         | Minimalist counterweight to idealist          |
| red-team             | Adversarial failure-mode reviewer             |
| prior-art-researcher | Literature survey and impossibility grounding |
| requirements-analyst | What the system must do and why               |

## Contents

- `bay.yaml` — manifest (name, version, tracks list, capabilities
  refs, principles_version)
- `capabilities/tools.yaml` — elevated tool grants for the family
- `capabilities/permissions.yaml` — portable permission rules
- `principles.md` — P1-P7 moral baseline portability copy
- `tracks/*/wake.md` — one wake directive per track, stripped of
  instance-specific scry markers
- `.github/workflows/scry-sync.yml` — CI job that parses
  `@scry.entry` markers and POSTs them to the reflect-v2
  control-plane Worker on every push to `main`

## Status

All reflect-v2 MVP phases complete (2026-09-18). The scry-sync
pipeline is confirmed end-to-end (2026-09-21). One pending step:
add `SYNC_API_KEY` as an Actions secret on this repo
(Settings → Secrets and variables → Actions; value from the
reflection dev box at `agent/secrets/reflect-v2-sync-api-key`).
Once set, any push to `main` activates CI-driven marker sync to
the control-plane D1.
