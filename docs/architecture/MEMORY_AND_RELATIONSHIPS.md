# Memory and Relationships

## Separation of Truth and Perspective

WORLD_SEED must preserve two valid but different records:

- **canonical events:** what the engine resolved;
- **resident memories and beliefs:** how a resident interpreted or retained those events.

A resident can misunderstand, forget, disagree, or revise a belief without changing the canonical event log.

## Memory Classes

| Class | Example | Visibility |
| --- | --- | --- |
| Objective world state | A door is open | Engine-owned; scoped observations |
| Shared event | Two residents completed an activity | Visible to authorized participants/observers |
| Episodic memory | “I enjoyed our first garden project” | Private to one resident by default |
| Semantic memory | A learned fact about a location | Private or world-shared by policy |
| Preference evidence | Repeatedly choosing quiet activities | Private, inspectable, confidence-based |
| Relationship belief | Trusting another resident more after repair | Perspective-specific and private |
| Creator-approved identity root | Name, boundaries, core background | Versioned configuration |
| Conversation context | Recent dialogue needed for coherence | Short-lived unless deliberately remembered |

## Memory Write Pipeline

1. A canonical event occurs.
2. The engine selects which residents observed or participated.
3. Each resident may receive a perspective-safe event summary.
4. A memory policy proposes candidate memories and salience.
5. Trusted code validates type, source references, privacy, and limits.
6. Accepted memories are stored with provenance and confidence.
7. Retrieval supplies only relevant, authorized context to the resident adapter.

Generated summaries never become objective truth merely because they were stored.

## Relationship Model

Relationships should not be reduced to one global score. A resident may maintain several bounded signals, for example:

- familiarity;
- trust;
- affection;
- respect;
- comfort;
- unresolved tension;
- shared-project history.

Signals are evidence summaries, not compulsory feelings or fixed story outcomes. Each resident owns its perspective. The engine may expose shared facts such as time spent together, but it must not declare a private interpretation for both sides.

## Corrections and Forgetting

Creators need tools to:

- inspect why a memory was retrieved;
- correct a false derived memory;
- mark disputed interpretations;
- forget selected private content;
- rebuild derived summaries from canonical events;
- export or delete a planted world's memory store.

Corrections should preserve an audit trail without retaining deleted sensitive content in ordinary logs.

## Privacy Defaults

- Personal memories are private to their resident.
- Shared events reveal only what each participant could observe.
- Relationship beliefs are not automatically reciprocal.
- Model prompts contain the minimum context needed for the current decision.
- Runtime memories never belong in a distributable world pack.
- Public diagnostics use synthetic or redacted data.

## Early Milestone Constraint

The first model-free vertical slice records events but does not infer rich memories or relationships. Memory begins only after event identity, provenance, inspection, and deletion are reliable.
