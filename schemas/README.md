# Draft Schemas

These JSON Schemas describe the `0.1-draft` public contracts. They are design artifacts and may change incompatibly before the first stable release.

| Schema | Purpose |
| --- | --- |
| [world-seed.schema.json](world-seed.schema.json) | Root `world.seed.yaml` or JSON manifest |
| [resident.schema.json](resident.schema.json) | Starting resident definition |
| [action.schema.json](action.schema.json) | Structured action proposal |
| [event.schema.json](event.schema.json) | Canonical event record |

YAML documents are validated after safe parsing into the equivalent JSON data model.

Schemas cannot enforce every security rule. Engines must additionally contain paths, resolve identifiers, check permissions and state revisions, enforce resource limits, and reject undeclared extensions.
