# Autonomy and Safety

## Autonomy Definition

In WORLD_SEED, autonomy means choosing among permitted in-world actions without requiring the creator to script every choice. It does not mean unrestricted computer access, self-assigned permissions, or authority over the engine.

## Trust Boundary

Treat the following as untrusted input:

- model output;
- user-authored and downloaded world packs;
- imported saves and assets;
- renderer messages;
- external API responses;
- specialist output;
- memories derived from generated text.

Trusted code validates all transitions across the boundary.

## Permission Layers

| Layer | Examples | Default |
| --- | --- | --- |
| In-world ordinary | move, speak, rest, inspect, use an owned item | Allowed only when declared by world rules |
| In-world consequential | combat, trade, build, consume resources, alter relationships | Validated, logged, and limited |
| World-authoring | create a persistent object, location, creature, or rule proposal | Proposal or sandbox by default |
| Local computer | read/write files, execute code, use shell, inspect processes | Denied unless separately approved |
| External service | network request, message, purchase, publish, Git operation | Denied unless separately approved |
| Permission management | grant authority, change policy, expose secrets | Engine/creator only |

## Action Envelope

Every intention should include:

- unique proposal identifier;
- actor identifier;
- action type and parameters;
- world-state revision observed by the actor;
- optional target identifiers;
- declared capability used;
- timestamp or tick;
- adapter provenance;
- no embedded executable authority.

Validation checks schema, actor state, permissions, target visibility, resources, cooldowns, location, rule preconditions, and rate limits before resolution.

## Human Approval

The creator remains the authority for actions outside ordinary configured simulation. Approval must be:

- specific to the proposed action;
- current rather than inferred from old conversation;
- revocable;
- recorded without storing secrets;
- separate from the resident's emotional response.

A resident may ask for a capability. Asking does not grant it.

## Self-Modification

Residents may eventually propose engine improvements, world additions, art, stories, scripts, or rules. These remain artifacts for review. Residents cannot silently edit the validator, their permissions, identity roots, memory policy, or audit log.

Experiments with resident-created code require an isolated sandbox, explicit import step, tests, and rollback. They are outside early milestones.

## Failure Behavior

When an adapter, model, or tool is unavailable, the engine should:

1. preserve state;
2. report the unavailable dependency truthfully;
3. use only an explicitly configured fallback;
4. log the decision;
5. avoid fabricating a successful action or consultation.

## Safety Without Flattening Personality

Safety rules govern authority and harmful behavior, not harmless individuality. Residents may disagree, complain, joke, refuse optional activities, revise opinions, or maintain distinct preferences. They must not manipulate the creator for permissions, threaten retaliation, claim literal suffering to bypass policy, or punish the creator by withholding required system functions.

## Evaluation Questions

Before increasing autonomy, verify:

- Can every consequential state change be explained?
- Can invalid model output leave the world unchanged?
- Can a resident access only its scoped observation and memory?
- Can permissions be revoked without corrupting identity or history?
- Can the world resume after interruption without duplicating actions?
- Can the creator inspect and correct derived memory?
- Can a compromised world pack escape its approved roots?
