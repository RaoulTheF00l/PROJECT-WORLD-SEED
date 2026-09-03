# Versioning and Compatibility

## Separate Version Domains

WORLD_SEED versions several contracts independently:

- public specification;
- engine release;
- world-seed manifest;
- resident, action, and event schemas;
- storage schema;
- adapter interfaces;
- individual world packs and rule extensions.

A pack must not assume that one matching number guarantees compatibility across every domain.

## Draft Versions

Design-stage contracts use labels such as `0.1-draft`. Drafts may change incompatibly. Every example and schema must state its draft version so early files cannot be mistaken for stable releases.

## Stable Versions

After the first stable release, use semantic versioning where practical:

- **major:** incompatible contract change;
- **minor:** backward-compatible capability;
- **patch:** backward-compatible correction.

File formats may use their own major/minor identifiers when full engine semantic versions would create unnecessary coupling.

## Compatibility Rules

- Engines reject unknown major seed versions.
- Engines may accept newer minor versions only when unknown-field behavior is defined.
- Packs declare a minimum engine version and explicit extension requirements.
- Adapters declare the interface versions they implement.
- Events record resolver and schema versions required for interpretation.
- Saves are never silently upgraded without a backup and migration report.

## Migration Contract

A migration must:

1. identify source and destination versions;
2. validate the source before transformation;
3. produce a new output or recoverable backup;
4. list renamed, added, removed, and transformed fields;
5. preserve stable identifiers whenever meaning is unchanged;
6. fail without modifying the original when conversion is unsafe;
7. support a dry run;
8. be covered by fixtures.

## Deprecation

Stable capabilities should be marked deprecated before removal. Documentation must name the replacement and earliest removal version. Security-critical behavior may be disabled sooner with a clear advisory and migration path.

## World-Pack Portability

The compatibility goal is not that every renderer or adapter supports every feature. It is that a pack can declare requirements and receive a complete, readable report before planting.
