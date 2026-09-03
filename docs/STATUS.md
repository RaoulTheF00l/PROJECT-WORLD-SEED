# Project Status

**Status date:** 2026-09-03  
**Specification version:** `0.1.0-draft`  
**Active milestone:** Milestone 1 — One Persistent Model-Free World Tick

## Verified

- The public project direction has been documented.
- Public engine concepts have been separated from private resident and world material.
- Draft JSON Schemas exist for a world seed, resident, action proposal, and canonical event.
- A character-neutral starter world pack exists for design and validation work.
- The private Python reference engine has passed 12 automated tests for canonical state, validation, event recording, deterministic order, and repeated ticks.
- Two deterministic placeholder residents can act in one room, producing ordered `wait` events while the world advances from tick `0` through tick `2`.
- Invalid world references and invalid actions fail before event-history mutation.
- The public repository contains no engine runtime or private world material.

See [Core Loop Proof](development/CORE_LOOP_PROOF.md) for the test manifest, supported claim, and evidence limitations.

## In Development

- JSON save, load, and resume behavior;
- restart and event-history preservation tests;
- conformance between private implementation types and the `0.1-draft` public schemas;
- replay checks and resolver-version recording;
- review of the `0.1-draft` seed vocabulary;
- final repository, contribution, and license policy;
- packaging boundaries for the private paid engine and public conformance tools.

## Planned Next

Complete Milestone 1 by adding versioned JSON persistence, save/load round-trip tests, restart-safe history, and deterministic replay evidence before any language model is connected.

## Not Implemented

- AI resident inference;
- personal memory or relationship development;
- voice, avatars, or renderer integration;
- creatures, combat, hunting, quests, or construction;
- external tools or resident-created code;
- payment, account, licensing, or distribution infrastructure;
- a stable public API.

Any document describing these subjects is a design direction, not proof of implementation.

The current evidence is verified in a private reference repository and cannot yet be independently reproduced from this public documentation repository. A public conformance harness remains planned.
