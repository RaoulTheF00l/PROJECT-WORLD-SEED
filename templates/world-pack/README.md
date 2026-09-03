# Tiny Garden Starter World Pack

Tiny Garden is a synthetic, character-neutral template for the `0.1-draft` WORLD_SEED specification. It shows how a small world pack may organize a manifest, location, residents, creature, and ruleset.

It is **not runnable yet** because the WORLD_SEED engine has not been implemented.

## Contents

```text
world-pack/
  world.seed.yaml
  locations/
    garden.yaml
  residents/
    gardener.yaml
    observer.yaml
  creatures/
    mossling.yaml
  rules/
    basic-rules.yaml
```

## Intended First Scenario

The planted world begins in one enclosed community garden. Two deterministic placeholder residents can observe, speak, wait, and use declared objects. A harmless mossling demonstrates that creatures can exist without loading combat or a language model.

The first engine milestone may use a fixed action sequence:

1. Gardener observes the dry planter.
2. Gardener uses the watering can on the planter.
3. The validator confirms location, capability, object state, and rule preconditions.
4. The transition marks the planter watered.
5. The event log records the accepted action.
6. Observer receives only the event details visible from the garden.
7. The world saves, reloads, and resumes at the next tick.

## Creating Your Own Pack

1. Copy this directory outside the WORLD_SEED engine repository.
2. Replace the pack identifier, title, and description.
3. Replace all synthetic locations, residents, creatures, and rules with original material.
4. Keep stable identifiers even if display names change.
5. Add one concept at a time and validate after each change.
6. Keep saves, memory, conversations, credentials, and model files outside the pack.
7. Choose licenses for your original world content and assets before distribution.

## Privacy Check

Before publishing a world pack, verify that it contains no:

- real personal information;
- private prompts or conversations;
- runtime memory or relationship history;
- credentials or local absolute paths;
- copyrighted characters, settings, or artwork without permission;
- model files without redistribution rights.

## Schema Coverage

The root manifest and resident files have draft schemas in [`../../schemas`](../../schemas/README.md). Location, creature, item, activity, quest, and ruleset schemas will be added through later specification milestones.
