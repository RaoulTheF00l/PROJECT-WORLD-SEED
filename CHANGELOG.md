# Changelog

All notable public specification changes will be recorded here.

This project uses design-stage version numbers until a functional engine is publicly released.

## 0.1.3-draft — 2026-09-03

### Added

- a 31-test private-reference evidence manifest;
- verified connected-room movement and safe room-construction claims;
- verified versioned JSON snapshot round-trip and temporary-file replacement claims;
- a documented immutable resident-observation and in-process action-provider boundary;
- an actor-binding guard that rejects a provider action attributed to a different resident.

### Changed

- advanced the private reference evidence beyond the original 12-test in-memory loop;
- moved JSON persistence, connected navigation, and the initial controller seam from planned to verified private-reference slices;
- narrowed the remaining Milestone 1 work to restart recovery, replay/digests, resolver versions, schema conformance, remaining actions, and stronger transaction guarantees;
- clarified that the controller seam is not a language-model adapter or proof of autonomous AI behavior.

### Not Included

- private engine source;
- a public conformance harness;
- process-restart, replay-digest, or full crash-durability evidence;
- language-model inference, Avatar input, memory, relationships, RPG rules, or renderer integration;
- a completed Milestone 1 claim.

## 0.1.2-draft — 2026-09-03

### Added

- a formal separation between the user's out-of-world Creator controls and human-controlled in-world Avatar;
- design contracts for resident-chosen roles and small institutions;
- an inspectable lifecycle for resident-led projects and collaborative world growth;
- glossary and architecture terms for human input, projects, roles, and institutions.

### Changed

- expanded the long-term experience from observing residents to sharing the world through an Avatar;
- expanded Milestone 5 with a terminal Avatar proof and explicit Creator/Avatar authority separation;
- reframed Milestone 8 around resident projects, roles, collaboration, validated imports, and visiting completed work;
- clarified that residents may invite or request help from the user without fabricating participation or gaining administrative authority.

### Not Included

- an implemented Avatar controller or user-input adapter;
- resident goal selection, roles, institutions, or project runtime state;
- automatic world generation or unrestricted model-driven modification.

## 0.1.1-draft — 2026-09-03

### Added

- a public evidence record for the private reference engine's first deterministic core loop;
- a 12-test behavioral manifest covering world validation, action validation, event recording, atomic rejection, resident ordering, and repeated ticks;
- explicit private-verification and public-reproducibility boundaries.

### Changed

- marked Milestone 0 verified and Milestone 1 active;
- separated completed in-memory core-loop behavior from unfinished persistence and replay work;
- updated status language so the repository is no longer purely aspirational.

### Not Included

- private engine source;
- persistence or restart evidence;
- a public conformance harness;
- a completed Milestone 1 claim.

## 0.1.0-draft — 2026-09-02

### Added

- public project proposal and repository boundary;
- system architecture and autonomy contract;
- staged development roadmap;
- draft world-seed, resident, action, and event schemas;
- world-pack, resident, RPG, adapter, and memory design documents;
- Tiny Garden starter world-pack template;
- proposed one-time $5 lifetime-access model;
- contribution and security guidance.

### Not Included

- engine runtime code;
- model integration;
- renderer integration;
- private resident or world material;
- a final software or content license.
