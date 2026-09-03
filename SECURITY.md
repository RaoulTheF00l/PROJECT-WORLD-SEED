# Security Policy

WORLD_SEED does not yet have a released engine. Security reports are still welcome for its proposed interfaces, schemas, examples, and future trust boundaries.

## Primary Threat Model

WORLD_SEED treats model output, imported world packs, generated assets, save files, and external content as untrusted input.

High-priority risks include:

- path traversal or access outside approved roots;
- prompt injection crossing from world content into tool authority;
- model-generated commands being treated as approved actions;
- unauthorized file, shell, network, Git, or credential access;
- malicious world packs or schema confusion;
- memory leakage between residents or worlds;
- event-log tampering or inconsistent state recovery;
- unsafe deserialization, dependency compromise, or plugin privilege escalation.

## Reporting

If GitHub private vulnerability reporting is enabled, use the repository's **Security** tab to submit a private report. Do not publish credentials, private data, or a working exploit in a public issue.

Include:

- the affected document, schema, version, or implementation revision;
- a concise reproduction or abuse path;
- expected and observed behavior;
- potential impact;
- a suggested containment strategy, if known.

## Security Principles

- Deny capabilities by default.
- Keep validation in trusted deterministic code.
- Use allowlisted roots, formats, actions, and adapters.
- Record consequential state transitions.
- Keep secrets and private memory outside world packs and logs.
- Fail closed when an adapter or permission service is unavailable.
- Make recovery and rollback testable before granting greater autonomy.
