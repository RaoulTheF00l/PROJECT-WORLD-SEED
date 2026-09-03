# World Seed Format

## Status

The world seed format is `0.1-draft`. It is a design contract, not a stable API.

## Purpose

The root seed manifest tells an engine how to validate and initialize a new world instance. It points to authored definitions and declares compatibility requirements. It does not contain mutable save data, private memories, conversations, credentials, or model files.

## Recommended Root File

Use `world.seed.yaml` at the root of a world pack.

```yaml
seed_version: 0.1-draft
id: example.tiny-garden
title: Tiny Garden
description: A deterministic starter world for validating one peaceful activity loop.

engine:
  minimum_version: 0.1.0

world:
  entry_location: location.garden
  clock:
    mode: tick
    ticks_per_day: 24

content:
  locations:
    - locations/garden.yaml
  residents:
    - residents/caretaker.yaml
  creatures:
    - creatures/mossling.yaml
  rules:
    - rules/basic-rules.yaml

requirements:
  adapters:
    - deterministic.policy

privacy:
  runtime_data: external
  include_private_memory: false
```

See the [draft JSON Schema](../../schemas/world-seed.schema.json) and [starter pack](../../templates/world-pack/README.md).

## Required Concepts

### `seed_version`

Version of the seed contract used by the manifest. Engines must reject unsupported major versions and report actionable compatibility errors.

### `id`

A stable namespaced identifier. It should not change when the title changes. Recommended pattern: `publisher.pack-name` using lowercase letters, digits, dots, underscores, and hyphens.

### `engine`

Declares the minimum compatible engine version. Later drafts may add an upper tested version without assuming incompatibility.

### `world`

Defines initialization rules such as entry location and clock mode. A seed establishes initial time behavior; each planted world stores its current clock separately.

### `content`

Lists relative paths to typed definitions. Paths must remain inside the world-pack root after normalization. Engines must reject traversal, absolute paths, device paths, and symbolic-link escapes.

### `requirements`

Declares adapter or extension identifiers required to plant the seed. Requirements never authorize installation or code execution automatically.

### `privacy`

Documents that runtime data is stored outside the pack. `include_private_memory` must remain `false` for distributable packs in the initial format.

## Planting Pipeline

1. Read the root manifest without executing pack code.
2. Validate syntax and the declared seed version.
3. Normalize and contain every referenced path.
4. Validate all referenced definitions.
5. Resolve required adapters against an approved registry.
6. Build an immutable initialization plan.
7. Ask for creator approval if new extensions or capabilities are required.
8. Create a new runtime identifier and private data root.
9. Write initial canonical state and a `world.planted` event.
10. Leave the source world pack unchanged.

## Seed Versus Runtime

| Seed/world pack | Planted runtime |
| --- | --- |
| Authored starting definitions | Evolving canonical state |
| Shareable by creator choice | Private by default |
| Version-controlled | Save and event storage |
| No conversation history | Resident memories and dialogue |
| No credentials | Local adapter configuration references |
| No model files | Runtime-selected model adapters |
| May be planted repeatedly | Has a unique instance identity |

## Determinism

If a pack uses randomness during initialization, the creator or engine supplies a seed value and records it in the initial event. Planting with the same pack version, initialization options, engine compatibility version, and random seed should produce the same canonical starting state.

## Evolution

Seed migrations must be explicit transformations from one version to another. An engine must never silently reinterpret an old pack under new semantics. Migration output should be reviewable before it replaces a creator's files.
