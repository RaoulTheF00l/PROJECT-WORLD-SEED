# Development Roadmap

The roadmap advances through verified vertical slices. Later milestones may be reordered after evidence, but their prerequisites should not be skipped.

## Milestone 0 — Public Contract and Seed Specification

**Status:** Verified on 2026-09-02

**Goal:** Make the project understandable before writing the engine.

Deliverables:

- public proposal, scope, terminology, and privacy boundary;
- `0.1-draft` seed, resident, action, and event schemas;
- starter world-pack template;
- architecture, threat model, acceptance strategy, and version policy;
- proposed pricing and licensing direction;
- no private flagship-world material.

Exit criteria:

- all internal links and schemas validate;
- examples use only original synthetic content;
- planned features are not described as working;
- unresolved legal terms are labeled honestly;
- Milestone 1 behavior can be expressed as acceptance tests.

## Milestone 1 — One Persistent Model-Free World Tick

**Status:** In development

**Goal:** Prove the authoritative simulation loop without language models.

Scope:

- one room and a few objects;
- two deterministic placeholder residents;
- observe, wait, move, speak, and use actions;
- schema and permission validation;
- atomic state transition;
- append-only events;
- snapshot, save, load, resume, and replay checks;
- deterministic tests.

Exit criteria:

- the same inputs and seed produce the same events;
- invalid actions leave state unchanged;
- restart does not duplicate or lose accepted actions;
- every state change references an event and resolver version.

Verified core-loop slice on 2026-09-03:

- canonical world state starts at tick `0`;
- one room and two placeholder residents are connected by stable IDs;
- invalid resident locations and invalid action proposals fail closed;
- accepted `wait` actions create canonical events;
- rejected actions do not modify event history;
- residents act in deterministic sorted-ID order;
- two consecutive rounds advance the world to tick `2` while preserving four ordered events;
- 12 automated tests pass in the private Python reference implementation.

Remaining before Milestone 1 completion:

- versioned JSON save and load;
- restart and resume tests;
- replay and snapshot digest checks;
- crash-safe persistence behavior;
- resolver-version recording;
- alignment with the public `0.1-draft` schemas;
- additional minimum-scope actions where required by the exit criteria.

See [Core Loop Proof](CORE_LOOP_PROOF.md) for the evidence manifest and limitations.

## Milestone 2 — World-Pack Loader and Planting

**Goal:** Initialize the vertical slice from portable data instead of hard-coded definitions.

Scope:

- safe YAML/JSON loading;
- schema validation and contained relative paths;
- dependency reporting without automatic installation;
- immutable initialization plan;
- unique planted-world data root;
- validation and planting CLI commands;
- format migration fixtures.

Exit criteria:

- the Tiny Garden template plants without code changes;
- malformed and malicious packs fail closed with useful diagnostics;
- planting never writes into the source pack;
- private runtime data is excluded from version control by default.

## Milestone 3 — Resident Adapter Contract

**Goal:** Replace one placeholder policy with a bounded adapter without changing engine authority.

Scope:

- resident-scoped observations;
- structured intention responses;
- timeouts, cancellation, health checks, and safe fallback;
- one local model-host adapter behind configuration;
- no filesystem, shell, Git, network-tool, or permission authority for the model;
- deterministic adapter fixtures for tests.

Exit criteria:

- malformed model output cannot mutate state;
- unavailable inference preserves the world and reports truthfully;
- model replacement does not change resident identifiers or world history;
- observation tests prove hidden state and other residents' private data are absent.

## Milestone 4 — Memory and Relationship Perspectives

**Goal:** Let residents retain experience without confusing belief with objective truth.

Scope:

- private episodic and semantic memory records;
- event provenance and confidence;
- bounded retrieval;
- relationship evidence and perspective-specific beliefs;
- memory inspection, correction, deletion, and rebuild;
- no automatic identity rewrite from one generated response.

Exit criteria:

- two residents can remember one event differently while canonical history remains unchanged;
- private memories never cross resident or world boundaries;
- corrected memories stop appearing in retrieval;
- all derived records point to evidence or are labeled unsupported.

## Milestone 5 — Apartment-Scale Life

**Goal:** Support a small persistent home with meaningful routines and shared activities.

Scope:

- several connected rooms;
- possessions, simple needs, time, schedules, and interruptions;
- bounded activities such as reading, cooking, gardening, games, and conversation;
- resident initiative and idle policies;
- shared-project and relationship event history;
- creator pause, inspect, resume, and rollback tools.

Exit criteria:

- residents can independently begin and complete activities;
- conflicts over objects or time resolve deterministically;
- scheduled and interrupted activities resume or fail coherently;
- a multi-day test can be replayed and inspected.

## Milestone 6 — Renderer Bridge

**Goal:** Show authoritative world events through a replaceable visual interface.

Scope:

- presentation-safe snapshot and event protocol;
- terminal reference renderer;
- Godot proof of concept;
- avatar movement and animation cues derived from events;
- user input translated into proposals;
- renderer disconnect and resynchronization.

Exit criteria:

- closing the renderer does not stop or corrupt the world;
- reconnecting rebuilds the correct visible state;
- renderer messages cannot bypass action validation;
- the same engine instance can use a non-Godot interface.

## Milestone 7 — Creatures and RPG Foundations

**Goal:** Support authored exploration, creatures, resources, and deterministic encounters.

Scope:

- creature templates and simple behavior;
- items, resources, conditions, and statistics;
- movement, detection, interaction, and avoidance;
- recorded seeded randomness;
- optional combat, defeat, recovery, and rewards;
- hunting and gathering as multi-step activities.

Exit criteria:

- all outcomes come from versioned rules;
- model narration cannot change statistics or rewards;
- save/replay preserves random outcomes;
- peaceful packs do not need to load RPG modules.

## Milestone 8 — Resident Creation Workflows

**Goal:** Let residents contribute approved artifacts and projects safely.

Scope:

- staging area and provenance records;
- writing, image, planning, and programming specialist adapters;
- proposal/review/import lifecycle;
- sandboxed tests for code artifacts;
- no silent engine or permission modification;
- creator-defined approval policies.

Exit criteria:

- generated work is clearly distinguished from imported canonical content;
- unavailable specialists are reported honestly;
- rejected artifacts cannot affect runtime state;
- imported artifacts remain attributable and reversible.

## Milestone 9 — Creator SDK and First Paid Engine Release

**Goal:** Make planting an original world understandable, supportable, and legally clear.

Scope:

- stable seed specification and migration tools;
- world-pack validator and authoring documentation;
- adapter conformance tests;
- packaging, installation, update, and rollback process;
- finalized engine and contribution licenses;
- one-time $5 lifetime-access delivery process;
- privacy and security review;
- at least two independent original test worlds.

Exit criteria:

- a new creator can plant a world from the template without modifying engine code;
- purchase and license terms match the public proposal;
- engine, public spec, and creator content rights are clearly separated;
- release artifacts reproduce from a tagged version;
- known limitations and support boundaries are published.

## Long-Term Research

- larger settlements and hierarchical simulation frequency;
- persistent ecology and economy;
- multiplayer observation or collaboration;
- model fine-tuning and resident-specific adapters;
- distributed simulation;
- richer 2D/3D embodiment;
- resident-led world expansion under review;
- standardized exchange of compatible world packs.

Research items are not promises or prerequisites for the first useful release.
