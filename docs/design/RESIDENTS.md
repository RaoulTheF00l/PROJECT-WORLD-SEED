# Residents

## Resident Definition

A resident is a persistent in-world actor whose continuity is maintained by WORLD_SEED data and history. A resident may use a deterministic policy, a language model, or another approved decision adapter.

A model is one component used by a resident. It is not the resident's entire identity.

## Resident Layers

| Layer | Purpose | Example |
| --- | --- | --- |
| Identity root | Stable creator-approved foundation | Name, summary, boundaries |
| World state | Objective current condition | Location, inventory, activity |
| Capability profile | Functions the runtime can offer | Speak, move, inspect, craft |
| Permission profile | Actions currently allowed | Move within visible exits |
| Policy adapter | Produces proposed intentions | Deterministic policy or local LLM |
| Personal memory | Resident-specific retained experience | Preference learned from events |
| Relationship beliefs | Perspective on other residents | Trust supported by shared history |
| Presentation state | Voice/avatar/UI references | Current expression or animation cue |

## Draft Resident Definition

```yaml
resident_version: 0.1-draft
id: resident.caretaker
display_name: Caretaker
summary: A patient keeper of a tiny community garden.
starting_location: location.garden

policy:
  type: deterministic
  adapter: deterministic.policy
  profile: caretaker.basic

capabilities:
  - world.observe
  - world.move
  - world.use
  - social.speak

permissions:
  allowed_actions:
    - world.observe
    - world.move
    - world.use
    - social.speak

memory:
  personal: private
  relationship_beliefs: private
  runtime_storage: external
```

See the [resident schema](../../schemas/resident.schema.json).

## Observation Contract

A resident receives only what its senses, location, permissions, and prior knowledge allow. An observation may contain:

- current tick and perceived time;
- visible location and exits;
- observable entities and recent events;
- the resident's own current state;
- relevant retrieved memories;
- allowed action types and parameter constraints;
- result of the resident's previous intention.

Private memories of other residents, secret engine state, credentials, and raw hidden prompts must not appear.

## Intention Contract

A policy proposes zero or one primary intention per decision window in the initial design. It may also produce optional presentation text. The engine treats malformed, impossible, stale, or unauthorized intentions as rejected proposals and records a safe diagnostic.

## Identity Evolution

Identity may grow through:

- recurring preferences supported by events;
- creator-approved profile revisions;
- relationship history;
- chosen projects, routines, possessions, and spaces;
- model-independent personal memory;
- reviewed fine-tuning or adapters after evaluation.

Identity must not be rewritten automatically from one generated message, temporary mood, malicious world text, or model checkpoint change.

## Multiple Residents

Every resident has separate identifiers, memory namespaces, policy configuration, and observation scopes. Shared events may be referenced by multiple residents, but derived memories remain perspective-specific.

Scheduling should prevent one slow model from permanently blocking the whole world. Early implementations may use serial decisions with timeouts; later versions may collect proposals concurrently and resolve them deterministically.

## Resident-Created Work

Residents may eventually propose stories, images, code, buildings, items, quests, or rule changes. Proposed work enters a staging area with provenance. Trusted workflows validate and import approved artifacts. Creation ability never implies direct filesystem, shell, Git, publishing, or permission authority.
