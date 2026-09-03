# Project Decisions

This log records accepted design direction. “Accepted” means the project will plan around the decision; it does not prove implementation.

## D-001 — WORLD_SEED Is a Reusable Engine Contract

**Status:** Accepted  
**Date:** 2026-09-02

WORLD_SEED exists to help other creators plant original persistent worlds. It is not the public repository for one private cast or setting.

## D-002 — Public Specification, Private Flagship World

**Status:** Accepted  
**Date:** 2026-09-02

Generic design, schemas, templates, and approved public components belong here. Creator-specific residents, assets, memories, relationships, and private world history belong in separate private storage.

## D-003 — Engine Owns Canonical Truth

**Status:** Accepted  
**Date:** 2026-09-02

Models propose structured intentions. Deterministic trusted code validates, resolves, applies, and records world changes.

## D-004 — World Packs Are Seeds, Not Saves

**Status:** Accepted  
**Date:** 2026-09-02

A world pack contains portable starting definitions. Each planted world stores evolving state, events, memories, and relationships separately.

## D-005 — Local-First and Adapter-Based

**Status:** Accepted  
**Date:** 2026-09-02

The deterministic core must not require cloud services. Models, specialists, renderers, storage, and tools connect through replaceable declared adapters.

## D-006 — One-Time $5 Lifetime Engine Access

**Status:** Accepted direction; legal terms pending  
**Date:** 2026-09-02

The official engine is intended to be offered for one $5 USD purchase with lifetime access and no required local-use subscription. The public specification remains separate.

## D-007 — Purchaser Forks Need a Precise Definition

**Status:** Provisional  
**Date:** 2026-09-02

Purchasers are intended to inspect and modify their own engine copy. Public redistribution, bundled runtimes, team access, and sublicensing remain unresolved until a final license is reviewed.

## D-008 — Python Reference Core, Godot as an Early Renderer

**Status:** Accepted direction  
**Date:** 2026-09-02

The private reference core is implemented in Python, and its first in-memory deterministic loop is covered by automated tests. Explicit JSON/YAML interfaces remain in development. Godot is an early presentation target but will not own world state.

## D-009 — Model-Free Core Before Model Integration

**Status:** Accepted  
**Date:** 2026-09-02

Persistence, actions, validation, events, and replay must work with deterministic placeholder policies before a language model is connected.

## D-010 — Optional RPG and Creation Layers

**Status:** Accepted direction  
**Date:** 2026-09-02

Creatures, combat, hunting, quests, crafting, specialist models, and resident-created artifacts use optional extension contracts rather than becoming mandatory assumptions.
