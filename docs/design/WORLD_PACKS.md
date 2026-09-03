# World Packs

## Definition

A world pack is a portable, creator-authored directory that supplies the starting content for a WORLD_SEED instance. It is comparable to a game module or campaign setting, but it is designed around persistent residents, inspectable state, and replaceable AI adapters.

## Suggested Layout

```text
my-world/
  world.seed.yaml
  README.md
  locations/
  residents/
  creatures/
  items/
  activities/
  rules/
  quests/
  assets/
  extensions/
```

Only directories used by a pack need to exist.

## Content Categories

### Locations

Define stable identifiers, descriptions, connections, tags, capacity, objects, and environmental properties. A renderer may add presentation data, but the engine retains authoritative topology and occupancy.

### Residents

Define starting identity roots, policy or adapter requirements, initial location, capabilities, and permission profile. Runtime memory and relationship history stay outside the pack.

### Creatures

Define species or templates, behavior policy, habitats, stats, resources, and interaction rules. Creatures need not use language models.

### Items and Resources

Define ownership, location, quantity, durability, tags, allowed uses, and crafting relationships. Rules resolve effects.

### Activities

Define bounded multi-step experiences such as reading, gardening, cooking, training, games, conversation, exploration, or collaborative creation.

### Rules

Declare action vocabulary, validation parameters, statistics, clocks, random tables, and extension requirements. Data-driven rules are preferred before executable plugins.

### Quests

Define optional goals, triggers, stages, rewards, and failure conditions without forcing a resident's emotional reaction.

### Assets

Store original or properly licensed presentation content. Asset licenses and attribution must travel with the pack.

## What Must Stay Out

A distributable world pack must not include:

- passwords, API keys, tokens, or machine-specific paths;
- private conversations or memory databases;
- planted-world saves or event logs unless deliberately exported and sanitized;
- model weights without redistribution rights;
- personal information used as hidden prompt context;
- copyrighted characters or settings without permission;
- executable extensions that are not declared and reviewed.

## Pack Validation

Validation should produce structured diagnostics with:

- severity;
- file and field path;
- rule identifier;
- human-readable explanation;
- suggested correction when safe;
- compatibility version.

Validation does not install adapters, download models, execute scripts, or plant the world.

## Extension Trust

The initial format supports data-only packs. Later executable extensions should be separated into signed or explicitly approved packages with declared permissions. Opening a world pack must never execute extension code.

## Creator Ownership

World-pack authors should retain ownership of their original residents, worlds, writing, rules, and artwork. The final engine license must clearly distinguish engine rights from creator-content rights and permit creators to choose separate licenses for their packs.

## Sharing Modes

A creator may keep a pack:

- private for a personal world;
- shared with selected collaborators;
- publicly downloadable;
- sold as original content if the final engine license permits the intended distribution method.

Runtime data remains separate in every mode.
