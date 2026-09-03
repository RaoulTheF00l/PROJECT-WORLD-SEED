# Resident Roles and Institutions

**Direction status:** Accepted design direction  
**Implementation status:** Planned

## Purpose

Residents should be able to develop meaningful places in their world without being permanently reduced to jobs assigned in a starting prompt. A resident may become interested in keeping an inn, organizing an adventurers' guild, maintaining a garden, teaching a craft, or pursuing another authored role because of experience, preference, opportunity, and collaboration.

Roles give repeated activity a durable structure. Institutions give multiple residents, locations, resources, and rules a shared structure.

## Roles Are World State

A role is a versioned relationship between an actor and a world function. It may include:

- a stable role identifier and display name;
- the resident or Avatar currently holding it;
- an institution or location it belongs to;
- permitted services and responsibilities;
- required capabilities, tools, schedules, or resources;
- when and why the role began;
- whether it is proposed, active, paused, vacant, shared, or retired;
- events supporting changes to the role.

A role is not created merely because a model says, “I am the guild master.” Trusted rules must confirm that the role exists, the actor accepted it, and any required institution or permissions are available.

## Role Lifecycle

```text
interest or need
    -> role proposal
    -> requirements and conflicts checked
    -> resident accepts or declines
    -> Creator approval where policy requires it
    -> role becomes active
    -> actions create evidence and history
    -> role changes, pauses, transfers, or ends
```

Residents should be allowed to change their minds. Leaving a role does not erase the work, relationships, or memories formed while holding it.

## Institutions

An institution is a canonical world entity that coordinates a continuing social function. Examples include an inn, guild, workshop, library, clinic, school, market stall, exploration team, or community garden.

An institution may reference:

- one or more locations;
- roles and membership rules;
- services and activities;
- schedules;
- owned or managed resources;
- authored rules for entry, trade, quests, work, or governance;
- founding, membership, and project events;
- current condition and unresolved needs.

Institutions do not receive unlimited authority. An innkeeper may manage declared rooms or services, but that role does not grant engine administration, filesystem access, or control over unrelated residents.

## Choice Without Pretending at Unlimited Emergence

WORLD_SEED can support resident initiative without claiming that every role appeared from nowhere. A resident chooses among opportunities that the current world and rules can represent. If a desired role requires a system that does not exist, the resident may begin a project and ask the Creator or collaborators for help.

The engine should distinguish:

- **available role:** already supported by current state and rules;
- **proposed role:** understandable but not yet approved or provisioned;
- **unsupported idea:** requires new design, assets, code, or permissions;
- **active role:** validated and currently held;
- **historical role:** ended but retained in history.

## Example: An Innkeeper

1. A resident repeatedly enjoys hosting visitors and preparing shared meals.
2. The resident proposes operating a small inn.
3. The proposal identifies a location, rooms, services, supplies, schedules, and missing requirements.
4. Other residents and the user may help design, write, illustrate, build, or provision it.
5. The Creator approves the import of any new definitions or assets.
6. The engine validates the institution and activates the innkeeper role.
7. The Avatar may visit, speak with the innkeeper, use declared services, and remember the opening.

## Example: An Adventurers' Guild

An adventurers' guild requires more than a title. Its first useful form might need:

- a known meeting location;
- a guild-master role;
- membership records;
- a small quest vocabulary;
- deterministic reward and completion rules;
- links to exploration and optional RPG systems;
- a process for proposing and approving new quests.

It should begin with one complete quest loop rather than a simulated bureaucracy with no usable behavior.

## Relationship to Identity

Roles can influence routine, reputation, skills, possessions, relationships, and memory, but they do not replace identity. A resident remains the same continuing actor when off duty, when a role ends, or when another resident takes over.

Models may interpret what a role means to them. Canonical state records which role exists and who holds it; personal memory records pride, frustration, attachment, disagreement, or changing preference.

## Initial Implementation Direction

The first role proof should use one existing location and one deterministic role with a narrow service. It should verify:

- proposal and acceptance;
- capability and resource checks;
- activation through a canonical event;
- one role-specific action;
- save and reload;
- voluntary pause or retirement; and
- no permission leakage beyond the role.

Complex economies, elections, autonomous law, large organizations, and cross-world institutions remain later research.
