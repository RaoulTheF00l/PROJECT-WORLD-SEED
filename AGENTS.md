# Instructions for Coding and Documentation Agents

These instructions apply to automated assistants working in the public WORLD_SEED repository.

## Current Project State

- WORLD_SEED is in **Milestone 1: One Persistent Model-Free World Tick**.
- Milestone 0 documentation and contract work are verified.
- A private reference implementation has verified the in-memory core-loop slice with 12 automated tests.
- Persistence, restart, replay, public-schema conformance, and public release remain incomplete.
- The public repository contains evidence documentation, draft schemas, and templates—not the private engine source.
- Do not expand the verified claim beyond [Core Loop Proof](docs/development/CORE_LOOP_PROOF.md).

## Public Repository Boundary

This repository must remain generic and safe to publish. Never add:

- the project creator's private residents, names, aliases, portraits, prompts, or biographies;
- private world locations, relationship plans, conversations, memories, or runtime history;
- personal information, credentials, tokens, machine paths, or private repository references;
- model weights, runtime databases, generated memory stores, or private training data;
- copyrighted settings, characters, logos, or artwork without explicit redistribution rights.

Use clearly synthetic examples such as the included Tiny Garden template.

## Engineering Invariants

1. The deterministic engine owns canonical world state.
2. Models return structured intentions; trusted code validates and applies them.
3. Model text never directly edits state, files, permissions, credentials, or external services.
4. Objective state, shared events, private memory, relationship beliefs, fiction context, and conversation context remain separate.
5. Model adapters, specialist models, renderers, and storage backends are replaceable boundaries.
6. RPG outcomes come from authored rules and recorded randomness, not narrative declarations.
7. Consequential operations are inspectable, permissioned, and reversible where practical.
8. A world pack contains starting definitions; mutable runtime history lives outside the pack.

## Working Rules

1. Work only within the active milestone unless the maintainer changes scope.
2. Inspect existing decisions and preserve unrelated changes.
3. Prefer small, testable Python modules and explicit data contracts.
4. Add the narrowest meaningful verification for every implemented rule.
5. Label status as **verified**, **in development**, **planned**, or **research**.
6. Keep examples deterministic and free of personal information.
7. Update schemas and prose together when an interface changes.
8. Do not silently settle unresolved legal, pricing, identity, or safety decisions.

## Milestone 1 Scope Guard

Milestone 1 includes:

- one small room;
- two deterministic placeholder residents;
- a minimal action vocabulary;
- action validation and state transitions;
- an append-only event log;
- save, load, resume, and tests.

Milestone 1 excludes language models, voice, Godot, networking, combat, hunting, construction, self-modification, paid distribution, and external tool execution.

## Documentation Style

- Lead with the current truth, then describe future direction.
- Use “resident” for an in-world actor and “model” for a replaceable inference component.
- Use “world pack” for portable authored definitions and “runtime state” for a planted world's evolving history.
- Prefer examples that teach one interface at a time.
- Link decisions to the document that owns them rather than duplicating conflicting rules.
