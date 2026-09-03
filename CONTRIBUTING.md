# Contributing to WORLD_SEED

WORLD_SEED is currently a design-stage project. The most useful contributions are focused reviews of the proposal, schemas, safety model, portability boundaries, and milestone plan.

## Before Contributing

Read:

1. [Project Proposal](docs/PROJECT_PROPOSAL.md)
2. [Project Status](docs/STATUS.md)
3. [System Architecture](docs/architecture/SYSTEM_ARCHITECTURE.md)
4. [Public/Private Boundary](docs/governance/PUBLIC_PRIVATE_BOUNDARY.md)
5. [AGENTS.md](AGENTS.md) if an automated assistant will participate

## Good Early Contributions

- identify contradictions or underspecified interfaces;
- improve a draft schema while preserving compatibility notes;
- propose small acceptance tests for the next milestone;
- add a completely original, privacy-safe example world pack;
- document adapter requirements for another local model host or renderer;
- report security or privacy risks with a reproducible scenario.

## Please Do Not Submit

- private prompts, memories, conversations, databases, or credentials;
- real personal data used as sample content;
- copyrighted characters, locations, or artwork without redistribution rights;
- generated claims that a planned feature already works;
- a large framework implementation before the relevant interface is accepted;
- code that lets model output bypass validation or permission checks.

## Change Process

1. Open an issue describing the problem, affected contract, and smallest useful outcome.
2. Separate facts, assumptions, and design preferences.
3. Keep each pull request focused on one decision or capability.
4. Include validation for schemas and tests for implemented behavior.
5. Update status and roadmap documents only when evidence supports the change.

## Contribution and License Notice

The public specification and future paid engine may use different licenses. Final contribution and redistribution terms have not yet been adopted. Until they are published, use issues for discussion and obtain maintainer agreement before submitting substantial code or reusable assets.

By submitting content, you confirm that you created it or have permission to contribute it and that it contains no private or restricted material.
