# Model, Specialist, Renderer, and Storage Adapters

## Why Adapters Matter

WORLD_SEED should outlive any one model server, checkpoint, renderer, or database. Adapters protect world and resident continuity by translating external systems into stable engine contracts.

## Adapter Types

### Resident model adapter

Receives a scoped observation, resident instructions, retrieved memory, allowed action vocabulary, and generation limits. Returns text for presentation and/or one structured intention.

It does not receive engine credentials or direct state mutation methods.

### In-process action provider precursor

The private reference implementation now verifies a smaller, model-free precursor to the resident model adapter. A callable receives one frozen resident observation and returns one structured action. The observation includes current tick, actor identity, current location, and available exit IDs; canonical `WorldState` is not passed through this interface.

The engine verifies that the returned action belongs to the resident whose decision was requested, then runs ordinary action validation. This seam can later sit behind a deterministic policy, human-input adapter, or local-model adapter, but it is not itself a model-host integration. It currently has no timeout, cancellation, health check, free-text parser, memory retrieval, or per-resident adapter registry.

See [Action Provider Boundary](ACTION_PROVIDER_BOUNDARY.md).

### Specialist adapter

Receives a bounded expert task—such as programming analysis, writing critique, image generation, or planning—and returns candidates or findings to the requesting resident workflow.

A specialist is not a resident, does not inherit identity, and cannot grant itself tools.

### Renderer adapter

Receives presentation-safe state snapshots and canonical events. It may send user input or avatar interaction proposals back through declared schemas. It never becomes the source of truth.

Terminal, web, 2D, 3D, accessibility, and Godot clients should be able to coexist behind this boundary.

### Storage adapter

Persists snapshots, events, memories, and metadata with transactional or recoverable behavior. Storage schemas are versioned independently from world-pack formats.

### Approved tool adapter

Wraps a narrow external capability such as reading an allowlisted project, generating an image, or exporting a creator-approved artifact. Tool calls require separate policy, input validation, provenance, and result handling.

## Common Adapter Contract

Every adapter should declare:

- adapter identifier and semantic version;
- interface versions supported;
- configuration schema;
- capabilities offered;
- data categories received and returned;
- whether network access is required;
- timeout and cancellation behavior;
- deterministic or stochastic behavior;
- failure codes and fallback rules;
- health-check method;
- privacy and logging behavior.

## Model Adapter Response

A resident model adapter should return an envelope similar to:

```json
{
  "adapter_version": "0.1-draft",
  "resident_id": "resident.caretaker",
  "utterance": "I'll water the dry planter.",
  "intention": {
    "action_type": "world.use",
    "parameters": {
      "target_id": "item.watering_can",
      "on_id": "object.planter"
    }
  },
  "diagnostics": {
    "fallback_used": false
  }
}
```

The engine independently validates the intention. An absent or invalid intention becomes no action, not an invitation to parse arbitrary prose.

## Local-First Direction

The first model integration should target a locally hosted HTTP interface. Cloud adapters may be contributed later, but must disclose transmitted data and remain optional. No adapter may make an online account mandatory for the deterministic core.

## Renderer Direction

Godot is an early renderer target because it supports 2D and 3D presentation, animation, input, and cross-platform export. The integration should consume events over a small protocol or library boundary so WORLD_SEED remains usable without Godot.

## Compatibility Testing

An adapter test suite should verify:

- declared version negotiation;
- valid and malformed response handling;
- timeouts and cancellation;
- unavailable dependency behavior;
- privacy-safe logging;
- capability scoping;
- deterministic fixtures where applicable;
- no state mutation outside the engine contract.
