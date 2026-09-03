# Business and Licensing Proposal

## Status

This document records project direction. It is **not** a final software license, purchase agreement, or legal opinion.

## Access Model

WORLD_SEED is proposed as two connected offerings.

### Public project layer

The public GitHub repository provides:

- the project proposal and roadmap;
- open technical discussion;
- world-seed and adapter specifications;
- schemas, validation examples, and starter templates;
- security, privacy, and contribution guidance.

The public repository does not contain the private flagship world or, under the current proposal, the paid engine implementation.

### Official engine layer

When a usable release exists, official engine access is intended to cost:

> **$5 USD once for lifetime access. No required subscription.**

“Lifetime access” is intended to mean continued purchaser access to official engine releases made available under the purchase terms. Payment processing, account recovery, team use, taxes, and support limits remain implementation decisions.

## Intended Purchaser Freedoms

The final engine license should aim to let a purchaser:

- install and run the engine locally;
- inspect source supplied with the purchase;
- create unlimited original world instances;
- modify a personal engine copy or maintain private derived branches;
- create original residents, worlds, rules, extensions, interfaces, games, and assets;
- keep those creations private, share them, or license them separately where technically and legally possible;
- retain ownership of original creator-authored content;
- continue using the purchased engine without recurring payment.

## Fork Terminology

In this proposal, “fork” means a purchaser-controlled modified copy or development branch of the engine. It does **not yet** promise the right to republish the complete engine source or provide unpaid engine access to third parties.

If public redistribution of full engine forks is later allowed, the $5 access charge becomes difficult to preserve because one purchaser could distribute a substitute copy. That tradeoff must be decided explicitly in the final license.

## Terms That Must Be Finalized Before Sales

- whether engine source or modified forks may be redistributed;
- whether a created world or game may bundle a compiled runtime;
- personal, household, team, and organization usage;
- commercial use of creator-made worlds and extensions;
- attribution and license-notice requirements;
- sublicense and transfer rules;
- update availability and account recovery;
- warranty, liability, termination, and refund terms;
- treatment of third-party dependencies and model licenses;
- contribution terms for public and paid components.

The project should use a qualified lawyer or a well-matched reviewed license before taking payment.

## Why a License Is Necessary

A public repository is not automatically open source. GitHub explains that without a license, default copyright applies and others may not reproduce, distribute, or create derivative works. See [GitHub: Licensing a repository](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).

Open-source licenses allow use, modification, and sharing, and must permit commercial use. That may conflict with preserving paid access to the engine itself. See the [Open Source Initiative definition](https://opensource.org/osd) and [commercial-use FAQ](https://opensource.org/faq).

For that reason, the likely engine category is **paid source-available software**, not freeware and not necessarily open source. The public specification may later receive a separate permissive documentation/schema license.

## Pricing Promise

The intended purchase is deliberately small and simple:

- one $5 payment;
- lifetime engine access for that purchaser;
- no mandatory subscription for local use;
- no requirement to buy individual worlds from the engine creator;
- no ownership claim over a purchaser's original world content.

Optional donations, hosted services, support, asset packs, or creator-made worlds may exist later, but they must be clearly separate from the base lifetime-access promise.

## Recommended License Split

Before the first release, evaluate:

1. a permissive license for public schemas and small examples;
2. a documentation license for public prose;
3. a paid source-available license for the engine;
4. creator-selected licenses for independent world packs and assets;
5. third-party notices for dependencies.

Do not copy a software license into the repository until the maintainer has intentionally accepted its consequences.
