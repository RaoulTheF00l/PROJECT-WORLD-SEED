# Core Loop Proof

**Evidence date:** 2026-09-03

**Implementation:** Private Python reference engine

**Milestone status:** Milestone 1 — In development

**Automated result:** 31 tests passed

**Public reproducibility:** Not yet available; engine source remains private

## Supported Claim

WORLD_SEED has a working model-free reference slice for deterministic ticks, validated waiting and connected movement, canonical event recording, safe room construction, versioned JSON snapshot persistence, and a bounded in-process action-provider seam.

This is broader than the original 12-test in-memory proof, but it is not completion of Milestone 1 and it is not evidence of language-model integration.

## What the Evidence Establishes

### Canonical state and deterministic ticks

The private reference implementation can:

1. construct a canonical world at tick `0`;
2. store rooms and residents by stable ID;
3. reject residents that reference nonexistent rooms;
4. reject rooms that reference nonexistent exits;
5. represent a proposed decision as a structured action;
6. validate the actor, action kind, target, and current navigation connection before mutation;
7. convert accepted actions into canonical events;
8. leave tested state and event history unchanged when an action is rejected;
9. process residents in sorted ID order; and
10. advance the world once after a successful deterministic round.

### Connected navigation and construction

The implementation supports `wait` and `move`. A move requires a known target room listed among the current room's exits. Accepted movement updates the resident's location and appends a movement event. Missing, unknown, and unconnected targets are rejected.

World-building helpers can create uniquely identified rooms and connect two known rooms in both directions. Repeating the same connection does not create duplicate exits. Missing endpoints and self-connections fail before the tested connection state is changed.

### Versioned snapshot persistence

The implementation can:

- serialize canonical state into a versioned JSON envelope;
- reconstruct nested room, resident, and event dataclasses from JSON;
- preserve ticks, connected-room exits, residents, and event history through round trips;
- reject unsupported save-format versions;
- reject semantically invalid world references before serialization and after deserialization;
- write a completed adjacent temporary file before replacing the destination; and
- replace an earlier save with a later snapshot.

This proves snapshot round trips within the test process. It does not yet prove process-restart recovery, power-loss durability, replay equivalence, or snapshot-digest equality.

### Bounded action-provider seam

An optional in-process callable can receive a frozen resident observation containing the current tick, active actor, current room, and immutable available-exit IDs. It may return a structured action for validation and application.

The engine rejects a provider action attributed to a different actor than the resident whose turn is active. Canonical `WorldState` is not passed through the provider interface.

This is a model-free controller seam. It is not a language-model adapter, security sandbox, Avatar interface, or proof of autonomous behavior.

## Current Reference Flow

```text
canonical WorldState
    -> validate world references
    -> build resident observation or use placeholder policy
    -> receive structured Action
    -> verify active actor
    -> validate action and room connection
    -> apply accepted transition
    -> append canonical Event
    -> advance completed tick
    -> serialize validated snapshot when requested
    -> write temporary file and replace destination
```

No language model participates in this proof. Without a custom action provider, the deterministic placeholder policy proposes `wait`.

## Test Evidence

The reference implementation was tested on Windows with Python `3.14.7`, pytest `8.4.2`, and this command:

```powershell
py -m pytest -v
```

The maintainer-observed result was `31 passed` followed by successful bytecode compilation with:

```powershell
py -m compileall src
```

### Canonical state, actions, and ticks

| Test | Contract demonstrated |
| --- | --- |
| `test_new_world_starts_empty` | A new world begins at tick `0` with empty collections. |
| `test_resident_can_be_placed_in_room` | Rooms and residents are stored and connected by stable IDs. |
| `test_valid_world_passes_validation` | A world with valid current references is accepted. |
| `test_world_rejects_missing_room` | A resident cannot reference a nonexistent room. |
| `test_valid_wait_action_passes_validation` | The `wait` action is accepted without a target. |
| `test_action_rejects_unknown_actor` | Unknown actors cannot act. |
| `test_action_rejects_unsupported_kind` | Undeclared action kinds fail closed. |
| `test_wait_action_rejects_target` | A wait proposal cannot carry a forbidden target. |
| `test_apply_wait_action_records_event` | An accepted wait produces and records a canonical event. |
| `test_rejected_action_does_not_modify_history` | A rejected action leaves event history unchanged. |
| `test_run_tick_processes_residents_in_deterministic_order` | Resident processing and emitted events use deterministic ID order. |
| `test_running_two_ticks_advances_time_twice` | Repeated ticks preserve history and advance time once per round. |

### Navigation rules

| Test | Contract demonstrated |
| --- | --- |
| `test_move_action_changes_resident_location` | Connected movement updates location and records a movement event. |
| `test_move_action_requires_destination` | A move without a target is rejected without mutation. |
| `test_move_action_rejects_unknown_destination` | A nonexistent movement target is rejected. |
| `test_world_rejects_missing_exit_room` | A room exit cannot reference a nonexistent room. |
| `test_move_action_rejects_unconnected_room` | A resident cannot teleport to a known but unconnected room. |

### Persistence rules

| Test | Contract demonstrated |
| --- | --- |
| `test_world_json_round_trip_preserves_state` | Versioned JSON preserves the complete tested state, including room exits. |
| `test_world_json_rejects_unsupported_save_version` | Unknown save versions fail explicitly. |
| `test_invalid_world_is_rejected_before_serialization` | Semantically invalid state is not serialized. |
| `test_deserialized_world_is_semantically_validated` | Parseable JSON must also satisfy world-reference rules. |
| `test_world_can_be_saved_and_loaded_from_file` | A filesystem round trip reconstructs equal but distinct state and consumes the temporary path. |
| `test_saving_again_replaces_previous_world` | A later snapshot replaces an earlier save. |

### World-building rules

| Test | Contract demonstrated |
| --- | --- |
| `test_add_room_creates_and_stores_room` | The builder creates and stores an initially unconnected room. |
| `test_add_room_rejects_duplicate_id` | A duplicate room ID cannot replace the original room. |
| `test_connect_rooms_creates_two_way_connection` | The helper creates matching exits in both rooms. |
| `test_connect_rooms_does_not_create_duplicates` | Repeating a connection is idempotent. |
| `test_connect_rooms_rejects_missing_room_atomically` | A missing endpoint cannot leave a half-created tested connection. |
| `test_connect_rooms_rejects_self_connection` | A room cannot be connected to itself through the helper. |

### Action-provider rules

| Test | Contract demonstrated |
| --- | --- |
| `test_action_provider_can_move_resident` | A custom provider receives the expected frozen navigation observation and can propose connected movement. |
| `test_action_provider_cannot_control_another_resident` | A provider cannot attribute the active resident's turn to another actor. |

## What This Does Not Yet Prove

The evidence does not yet demonstrate:

- a process exiting, restarting, loading, and resuming without duplicate work;
- deterministic replay or snapshot/event digests;
- resolver-version recording;
- full crash durability, directory synchronization, or recovery from an interrupted replacement;
- whole-tick transaction rollback when an earlier resident acted before a later failure;
- conformance between private Python types and the public `0.1-draft` schemas;
- world-pack validation or planting;
- `speak`, `use`, inventory, schedules, or other Milestone 1 actions;
- language-model inference, model-response parsing, timeouts, cancellation, or fallback behavior;
- per-resident models, private memory, relationships, goals, roles, or projects;
- human Avatar input or Creator controls;
- renderer, Godot, RPG, creature, combat, hunting, construction, networking, or external-tool behavior.

## Evidence Boundary

The implementation and its repository remain private. This public evidence record documents maintainer-observed tests, exact behavioral claims, and known limitations, but it is not an independent source audit. A public conformance harness and tagged release evidence are still required before a public engine release.

The claim supported today is deliberately narrow:

> A private, model-free Python reference implementation has passed 31 automated tests for deterministic ticks, validated waiting and connected movement, canonical events, safe room construction, versioned JSON snapshot round trips, semantic persistence validation, and an actor-bound in-process action-provider seam.
