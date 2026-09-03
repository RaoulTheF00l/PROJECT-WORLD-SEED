# Public and Private Repository Boundary

## Purpose

WORLD_SEED separates the reusable engine contract from each creator's personal world. This prevents one flagship installation from becoming the hard-coded definition of the platform and reduces the chance of publishing private history by accident.

## Public WORLD_SEED Repository

May contain:

- project proposal and design principles;
- generic architecture and safety rules;
- schemas and compatibility contracts;
- synthetic example packs;
- public roadmap and verified status;
- contribution, security, pricing, and license proposals;
- future public SDK components explicitly approved for release.

Must not contain:

- private resident identities, prompts, portraits, or biographies;
- relationship plans or accumulated relationship history;
- private locations, conversations, journals, or memories;
- creator personal information or machine paths;
- runtime databases, event logs, saves, or model files;
- private training examples or evaluation transcripts;
- unlicensed third-party characters, settings, logos, or artwork.

## Private Flagship-World Repository

May contain creator-specific:

- resident definitions and identity roots;
- world lore, locations, activities, creatures, items, and quests;
- portraits, voices, rigging, models, and authored assets;
- adapter configuration that contains no committed secret;
- private tests and migration scripts;
- reviewed world-pack source.

It should still exclude credentials and mutable runtime data from Git history.

## Private Runtime Data

Store outside both source repositories by default:

- canonical save state;
- append-only event history;
- personal and relationship memories;
- conversations and journals;
- generated artifacts awaiting review;
- caches, embeddings, logs, and diagnostics;
- tokens, credentials, device configuration, and model host details.

Runtime exports require an explicit destination and privacy review.

## Reference Layout

```text
WORLD_SEED/                 public specification and approved public components
my-private-world/           private authored world pack
world-seed-runtime-data/    private planted state, events, and memory
```

These paths are conceptual. The runtime must support creator-selected locations and never assume a home-directory layout.

## Dependency Direction

The private world may depend on the public specification and paid engine. The public repository must never depend on or import the private world.

Generic improvements discovered while building a private world may be proposed publicly only after names, data, examples, assets, paths, and history have been replaced with synthetic material.

## Publication Checklist

Before publishing a commit or release:

- search for private resident and world names;
- inspect added images and asset rights;
- scan for secrets, emails, usernames, paths, and database files;
- verify examples are synthetic;
- confirm status claims match tests;
- ensure ZIP archives exclude `.git`, saves, logs, caches, and hidden environment files;
- review the final file list from the archive itself.
