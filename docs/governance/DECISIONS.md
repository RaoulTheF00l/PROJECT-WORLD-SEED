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

## D-011 — The User Has Separate Creator and Avatar Roles

**Status:** Accepted direction  
**Date:** 2026-09-03

The Creator manages approvals, configuration, privacy, recovery, and administration outside the fiction. The human-controlled Avatar participates inside the world through the same validated action boundary used by other actors. Neither control path silently inherits the authority of the other.

## D-012 — Residents May Initiate World-Growth Projects

**Status:** Accepted direction  
**Date:** 2026-09-03

Residents may develop goals, propose additions, collaborate with other residents and the user, and ask for missing help. Proposals and generated artifacts remain staged until trusted validation and any required Creator approval allow canonical import.

## D-013 — Roles and Institutions Are Canonical, Voluntary Structures

**Status:** Accepted direction  
**Date:** 2026-09-03

Roles such as innkeeper or guild master are not permanent prompt labels or self-declared authority. They are inspectable world records with requirements, scoped permissions, status, acceptance, and event history. Residents may change or leave roles without erasing identity.

## D-014 — Controllers Receive Observations and Return Proposals

**Status:** Accepted

**Date:** 2026-09-03

A resident policy, future model adapter, or human-input adapter should receive a bounded observation instead of direct canonical mutation authority. It returns a structured action proposal for the actor whose decision was requested. Trusted engine code verifies actor binding, validates the proposal, applies accepted changes, and records the event. A private model-free reference slice now verifies this boundary for an in-process callable; external adapters remain planned.
