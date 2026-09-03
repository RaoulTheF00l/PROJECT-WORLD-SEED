# Project Status

**Status date:** 2026-09-03

**Specification version:** `0.1.3-draft`

**Active milestone:** Milestone 1 — One Persistent Model-Free World Tick

## Verified

- The public project direction has been documented.
- Public engine concepts have been separated from private resident and world material.
- Draft JSON Schemas exist for a world seed, resident, action proposal, and canonical event.
- A character-neutral starter world pack exists for design and validation work.
- The private Python reference engine has passed 31 automated tests.
- Deterministic placeholder residents can produce ordered `wait` events while the world advances through repeated ticks.
- Validated `move` actions change location only across declared room exits and produce canonical movement events.
- Missing destinations, unknown rooms, unconnected rooms, invalid world references, and invalid actions fail before the tested state or event history is mutated.
- Safe builder helpers add uniquely identified rooms and create idempotent two-way connections without partial links.
- Versioned JSON serialization preserves rooms, exits, residents, ticks, and event history across in-memory and filesystem round trips.
- Saving writes a completed temporary file before replacing the destination, and repeated saves replace the previous snapshot.
- Serialization and deserialization both apply semantic world validation.
- A pluggable in-process action provider receives a frozen resident observation and may return a structured action; an action returned for a different resident is rejected.
- The public repository contains no engine runtime or private world material.
- The accepted long-term design now separates Creator administration from human-controlled Avatar actions and defines resident-led roles, institutions, and world-growth projects.

See [Core Loop Proof](development/CORE_LOOP_PROOF.md) for the test manifest, supported claim, and evidence limitations.

## In Development

- process-restart and resume behavior;
- replay and snapshot-digest equality;
- whole-tick transaction and rollback behavior when a later resident action fails;
- conformance between private implementation types and the `0.1-draft` public schemas;
- replay checks and resolver-version recording;
- review of the `0.1-draft` seed vocabulary;
- final repository, contribution, and license policy;
- packaging boundaries for the private paid engine and public conformance tools.

## Planned Next

Complete Milestone 1 by adding process-restart recovery, deterministic replay and snapshot-digest evidence, resolver-version recording, remaining minimum-scope actions, and public-schema alignment before any language model is connected.

## Not Implemented

- AI resident inference or a model-host adapter;
- personal memory or relationship development;
- voice or renderer integration;
- human Avatar input, resident goal selection, roles, institutions, or resident-led project state;
- creatures, combat, hunting, quests, or construction;
- external tools or resident-created code;
- payment, account, licensing, or distribution infrastructure;
- a stable public API.

Any document describing these subjects is a design direction, not proof of implementation.

The current evidence is verified in a private reference repository and cannot yet be independently reproduced from this public documentation repository. The in-process action provider is an engine seam, not evidence of AI integration or autonomous resident behavior. A public conformance harness remains planned.
