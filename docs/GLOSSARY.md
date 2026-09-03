# Glossary

## Action Proposal

A structured request from a resident policy, model adapter, user interface, or deterministic system. It contains an actor, action type, parameters, and observed-state reference. It has no effect until validated.

## Adapter

A replaceable boundary between WORLD_SEED and an external component, such as a language-model host, renderer, storage backend, specialist model, or approved tool.

## Avatar

The human-controlled in-world actor through which a user can speak, travel, participate, and interact under ordinary world rules. Avatar authority is separate from Creator administration.

## Canonical Event

An immutable record of a validated occurrence or state transition. Events identify what happened, when, why, and which rule resolved it.

## Canonical State

The engine-owned objective representation of the current world. Residents may hold beliefs about state, but only the engine changes canonical state.

## Capability

A function the runtime can technically perform. A capability does not imply that a resident has permission to request or use it.

## Creator

The human owner or operator of a planted world acting through explicit configuration, approval, inspection, recovery, and administration controls. The Creator may also control an Avatar, but the two roles use different authority paths.

## Engine Core

The deterministic modules responsible for time, state, validation, transitions, events, persistence, and extension coordination.

## Event Log

The ordered, append-only history of canonical events used for inspection, replay, recovery, and memory inputs.

## Human Input Adapter

A boundary that converts direct user input for an Avatar into a structured action proposal. It does not apply state changes without validation.

## Institution

A canonical world entity coordinating an ongoing social function through locations, roles, members, services, resources, schedules, and authored rules.

## Planted World

A runtime instance created from a world seed. It owns evolving saves, events, private memories, and instance-specific creations.

## Resident

An in-world actor with a stable identifier, profile, capabilities, permissions, observations, policy or model adapter, and private perspective. A resident is not identical to its current model checkpoint.

## Resident Policy

The component that proposes a resident's next intention. Early policies may be deterministic placeholders; later policies may consult language models.

## Resident Goal

A bounded desired outcome derived from a resident's perspective, preferences, needs, opportunities, or current projects. A goal is not proof that its outcome is possible or approved.

## Resident Project

An inspectable record through which residents and the user may plan, stage, validate, approve, and realize a proposed artifact or world addition.

## Role

A versioned relationship between an actor and a world function, including its scope, requirements, permissions, status, and supporting history. A role is not a replacement for identity.

## Rule Set

Versioned deterministic logic that decides whether actions are allowed and how they affect state.

## Runtime History

Mutable, instance-specific state accumulated after planting: events, saves, memories, relationships, projects, discoveries, and consequences.

## Specialist

A bounded model or service consulted for focused expertise such as programming, writing, image generation, planning, or classification. A specialist is a capability, not a separate resident or authority.

## Structured Intention

The normalized action proposal returned by a resident adapter. It uses a known action type and schema rather than free-form claims.

## World Pack

A portable directory of authored world definitions, assets, manifests, and rules. It contains starting material, not a planted world's mutable private history.

## World Seed

The versioned root manifest that identifies a world pack, its dependencies, starting entities, rule sets, adapter requirements, and initialization options.
