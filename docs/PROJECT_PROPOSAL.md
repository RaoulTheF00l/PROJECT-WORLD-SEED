# WORLD_SEED Project Proposal

## Proposal Summary

WORLD_SEED will be a local-first simulation engine that lets creators define and run persistent fictional worlds shared by AI residents and a human-controlled avatar. Instead of shipping a fixed cast or setting, WORLD_SEED supplies the deterministic machinery needed to **plant a world seed** and allow that installation to develop its own history.

The project will publish its vision, interoperability specification, schemas, templates, safety model, and development record in a public repository. The official engine implementation is proposed as a source-available product offered for a one-time **$5 USD lifetime purchase** when it reaches a usable release.

## The Problem

Most character-chat systems center on a conversation window. Their characters may sound consistent for a session, but they rarely inhabit an authoritative world with durable objects, locations, time, consequences, shared events, separate memories, and rules that cannot be rewritten by narration.

Game engines solve state and rendering but generally do not define safe interfaces for persistent AI residents. Agent frameworks provide tools and workflows but often treat agents as task workers rather than inhabitants of a fictional environment.

WORLD_SEED proposes a bridge between those categories.

## The Vision

A creator should be able to define:

- a small apartment, village, ship, school, wilderness, or original setting;
- one or more distinct residents;
- a human-controlled Avatar through which the user can participate inside the world;
- daily activities and social opportunities;
- creatures, items, resources, abilities, and optional RPG mechanics;
- model providers and specialist capabilities;
- a visual interface ranging from a terminal to a game engine;
- strict privacy, memory, and permission boundaries.

After initialization, the engine should maintain objective state and history. Residents receive bounded observations, propose structured intentions, and receive the results of validated actions. Their routines, preferences, projects, conflicts, relationships, and interpretations can then develop from actual recorded experience.

## The Core Experience

WORLD_SEED is intended to support a world that can be expanded from within rather than only edited from an external authoring screen.

A resident may develop an interest in operating an inn, forming an adventurers' guild, maintaining a workshop, building a home, documenting creatures, or creating another world-supported project. Residents may plan together, contribute through bounded specialist capabilities, identify missing requirements, and ask the user for help. Their work enters canonical state only through structured projects, validation, provenance, and Creator approval where required.

The human participant has two distinct modes:

1. **Creator mode** manages the installation, approvals, configuration, recovery, and development inputs.
2. **Avatar mode** allows the user to enter the world, interact with residents, explore, and participate through validated in-world actions.

This separation lets a resident truthfully say, “We opened the inn—make an Avatar and visit us,” without confusing an invitation with administrator authority or pretending the user already participated.

## Product Definition

WORLD_SEED consists of four conceptual layers:

1. **Engine core** — authoritative state, time, action validation, transitions, event history, persistence, and deterministic rules.
2. **World pack** — portable authored starting definitions such as locations, residents, creatures, items, activities, and rulesets.
3. **Adapters** — replaceable connections to language models, memory stores, renderers, interfaces, specialist models, and approved tools.
4. **Runtime instance** — one planted world's evolving state, private memories, relationships, events, and creator-specific assets.

The public repository defines how these layers interact without exposing any private flagship world.

## Intended Audience

- hobbyists building personal AI worlds;
- writers exploring persistent character ecosystems;
- indie game developers prototyping autonomous residents;
- researchers studying inspectable multi-agent simulations;
- educators teaching state machines, simulation design, AI boundaries, or event sourcing;
- creators who want local control over models and personal data.

## Foundational Requirements

The engine should be:

- **local-first:** a core world can run without a mandatory hosted account or cloud service;
- **model-agnostic:** no resident identity is tied permanently to one checkpoint or vendor;
- **deterministic at the rule boundary:** randomness is seeded and recorded;
- **inspectable:** actions, state transitions, and important memory writes can be reviewed;
- **portable:** world packs use versioned documented formats;
- **privacy-preserving:** private runtime history is separated from shareable definitions;
- **extensible:** RPG rules, renderers, model hosts, and creator tools use explicit adapters;
- **resource-conscious:** the first usable world should not require a server cluster or high-end GPU;
- **participatory:** the user can enter through an Avatar without surrendering separate Creator controls;
- **co-creative:** resident-led growth uses finite projects, staged work, validation, approval, and recorded provenance.

## Non-Goals

WORLD_SEED is not intended to:

- prove AI consciousness, personhood, souls, or literal suffering;
- give model output unrestricted computer or network control;
- let residents silently rewrite the engine that validates their actions;
- replace a general-purpose game engine;
- ship copyrighted fictional universes or character likenesses;
- guarantee human-like intelligence, perfect memory, or emergent relationships;
- begin as a massively multiplayer world or planetary-scale simulation.

## Initial Deliverables

### Public specification

- world-seed manifest and world-pack layout;
- action, event, resident, memory, and adapter contracts;
- reference schemas and privacy-safe templates;
- architecture, threat model, roadmap, and acceptance tests.

### Engine foundation

- deterministic tick loop;
- validated state transitions;
- append-only event history;
- save, load, and resume;
- resident and adapter interfaces;
- command-line inspection tools;
- automated tests and migration support.

### Expansion layers

- local-model adapters;
- bounded memory and relationship interpretation;
- activities, projects, creatures, resources, combat, hunting, and RPG hooks;
- user-Avatar interaction, resident-chosen roles, institutions, and resident-led world growth;
- renderer bridge, with Godot as an early target;
- approved resident creation workflows and specialist adapters.

## Development Strategy

WORLD_SEED will grow through narrow vertical slices. Each milestone must produce observable behavior, tests, and a truthful status update. Language models enter only after the model-free state engine is reliable. Rich autonomy enters only after memory, permissions, recovery, and evaluation are inspectable.

See the [Development Roadmap](development/ROADMAP.md).

## Public Repository Strategy

The public repository is the project's front door and interoperability contract. It should remain useful even to someone who implements a compatible engine independently. It contains no creator-specific residents, private memories, personal artwork, or private world history.

Creators keep their own world packs public or private as they choose. Mutable saves and personal memory stores remain private by default.

## Sustainability Proposal

The intended official-engine offer is:

- one payment of **$5 USD**;
- lifetime access to the purchaser's official engine releases under the final purchase terms;
- access to source sufficient to create personal modifications;
- no required subscription for the local engine;
- freedom to create original world packs and extensions;
- clear separation between the engine license and ownership of creator-made content.

The exact rights for distributing modified engine source, bundled runtimes, team use, and commercial projects must be settled in a reviewed license before payment is accepted. The public documentation must not promise terms that the final license cannot support.

## Success Criteria

WORLD_SEED succeeds when a new creator can:

1. copy the starter template;
2. define an original world and residents without editing engine code;
3. validate and plant the seed;
4. run, stop, save, and resume the world deterministically;
5. inspect why an action succeeded or failed;
6. replace a model or renderer adapter without destroying identity or history;
7. keep private runtime data out of public source control;
8. control an Avatar that participates through the world's ordinary action rules;
9. let residents propose one small world addition and collaborate with the user through an inspectable approval process; and
10. build and distribute original world content under clear terms.

## Immediate Decision

Maintain this repository as the public specification, proposal, and evidence index. Keep the creator's flagship world and paid reference-engine source in separate private repositories. Milestone 0 is complete, and the private reference now verifies versioned snapshot persistence plus a model-free action-provider seam. Finish process-restart recovery, replay/digests, resolver-version recording, remaining actions, stronger transaction guarantees, and schema-conformance evidence for Milestone 1 before connecting a language model.
