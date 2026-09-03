# Core Loop Proof

**Evidence date:** 2026-09-03  
**Implementation:** Private Python reference engine  
**Milestone status:** Milestone 1 — In development  
**Automated result:** 12 tests passed  
**Public reproducibility:** Not yet available; engine source remains private

## What This Evidence Establishes

WORLD_SEED now has a working, model-free proof of its authoritative simulation loop. The private reference implementation can:

1. construct a canonical world at tick `0`;
2. store one room and two placeholder residents by stable ID;
3. reject residents that reference nonexistent rooms;
4. represent a resident decision as a structured action proposal;
5. validate the actor, action kind, and target rules before mutation;
6. convert an accepted `wait` action into a canonical event;
7. leave event history unchanged when an action is rejected;
8. process residents in sorted ID order;
9. advance the world exactly once after all residents act; and
10. repeat the loop from tick `1` to tick `2` without losing prior events.

The current flow is:

```text
WorldState at tick 0
    -> validate world
    -> choose deterministic placeholder action
    -> validate action
    -> apply action
    -> append canonical event
    -> advance to tick 1
```

No language model participates in this proof. The temporary resident policy always proposes `wait`, keeping the test deterministic.

## Test Evidence

The reference implementation was tested on Windows with Python `3.14.7`, pytest `8.4.2`, and this command:

```powershell
py -m pytest -v
```

The maintainer-observed result was `12 passed`.

| Test | Contract demonstrated |
| --- | --- |
| `test_new_world_starts_empty` | A new world begins at tick `0` with empty collections. |
| `test_resident_can_be_placed_in_room` | Rooms and residents are stored and connected by stable IDs. |
| `test_valid_world_passes_validation` | A structurally valid world is accepted. |
| `test_world_rejects_missing_room` | A resident cannot reference a nonexistent room. |
| `test_valid_wait_action_passes_validation` | The currently supported `wait` action is accepted. |
| `test_action_rejects_unknown_actor` | Unknown actors cannot act. |
| `test_action_rejects_unsupported_kind` | Undeclared action kinds fail closed. |
| `test_wait_action_rejects_target` | An action cannot carry a target forbidden by its rules. |
| `test_apply_wait_action_records_event` | An accepted action produces and records a canonical event. |
| `test_rejected_action_does_not_modify_history` | Rejected actions leave event history unchanged. |
| `test_run_tick_processes_residents_in_deterministic_order` | Resident processing and emitted events have deterministic order. |
| `test_running_two_ticks_advances_time_twice` | Repeated ticks preserve history and advance time once per round. |

## What This Does Not Yet Prove

This is a proof of the smallest core loop, not completion of Milestone 1. It does not yet demonstrate:

- JSON save, load, or restart recovery;
- replay or snapshot digest equality;
- crash-safe atomic persistence;
- conformance between the private Python types and the public `0.1-draft` schemas;
- actions other than `wait`;
- resolver-version recording;
- world-pack loading;
- language-model, memory, relationship, renderer, RPG, or networking behavior.

## Evidence Boundary

The implementation and its repository remain private because they are intended to become part of the paid engine. This public evidence record documents the exact tested contracts and known limitations, but it is not an independent source audit. A public conformance harness and tagged release evidence are still required before a paid engine release.

The claim supported today is deliberately narrow:

> A private reference implementation has passed automated tests for a deterministic two-resident core loop with validated `wait` actions and canonical event history.
