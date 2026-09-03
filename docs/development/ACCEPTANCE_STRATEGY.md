# Acceptance Strategy

## Evidence Before Status

A WORLD_SEED capability becomes **verified** only when a reproducible check demonstrates its user-visible contract. A document, schema, prompt, mockup, generated answer, or successful import is not sufficient evidence by itself.

## Status Vocabulary

| Label | Meaning |
| --- | --- |
| Research | Being explored; no committed interface |
| Planned | Accepted direction without implementation |
| In development | Implementation exists but exit criteria are incomplete |
| Verified | Reproducible checks satisfy the documented contract |
| Deprecated | Still present temporarily but scheduled for removal |

## Test Layers

### Schema tests

- valid examples pass;
- missing required fields fail;
- unknown fields follow the declared compatibility policy;
- paths reject traversal and absolute locations;
- identifier and version formats are enforced.

### Rule tests

- preconditions allow and deny the expected actions;
- invalid proposals never partially mutate state;
- resource costs and outcomes match authored rules;
- seeded randomness reproduces exactly;
- resolver versions are recorded.

### Persistence tests

- save and load preserve canonical state;
- event ordering and identifiers survive restart;
- a crash cannot duplicate an accepted transition;
- replay reaches the expected snapshot hash;
- migrations preserve or explicitly transform meaning.

### Privacy tests

- one resident cannot retrieve another's private memory;
- one world cannot read another world's runtime directory;
- diagnostics redact secrets and personal data;
- public exports omit saves, conversations, and private adapter configuration;
- malicious paths remain inside the approved root.

### Adapter contract tests

- timeouts, malformed results, and unavailable services fail safely;
- capability declarations match callable behavior;
- model text cannot bypass structured intention validation;
- renderer input cannot directly mutate state;
- fallback behavior is explicit and observable.

### Scenario tests

Small end-to-end fixtures should answer concrete questions:

- Can a resident observe a usable item and propose a valid use action?
- Does a stale proposal fail if another action changed the target first?
- Can the world stop after the event and resume without changing history?
- Do two residents receive different authorized observations?
- Does a rejected action produce a diagnostic without a state event?

## Milestone Evidence Packet

Every completed milestone should publish:

- tagged source revision;
- acceptance criteria and test command;
- test result summary;
- example input and resulting events;
- known limitations;
- migration or rollback instructions when applicable;
- updated [Project Status](../STATUS.md).

## Avoiding False Emergence Claims

Claims about preferences, relationships, planning, creativity, or autonomy require event history and evaluation—not a compelling transcript. Public demonstrations should separate:

- authored starting conditions;
- model-generated language;
- deterministic engine decisions;
- derived memory or relationship signals;
- creator interpretation.

## First Acceptance Target

Milestone 1 is accepted when a model-free Tiny Garden fixture can run a fixed sequence, reject an invalid action, save, reload, resume, and produce the same final state and event digest on repeated runs.

## Current Milestone 1 Evidence

As of 2026-09-03, the private reference implementation passes 12 automated tests for the in-memory portion of this target. The tests cover canonical state, valid and invalid world references, valid and invalid actions, event recording, rejected-action atomicity, deterministic resident order, and repeated tick advancement.

Persistence, restart recovery, replay digests, public-schema conformance, and a public conformance harness remain incomplete. Milestone 1 is therefore **in development**, not accepted.

See [Core Loop Proof](CORE_LOOP_PROOF.md) for the exact test manifest and supported public claim.
