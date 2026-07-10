# Event Formats

> [Home](../README.md)

## Overview

The Community Event Hub supports different types of events. An event defines **what is being organized**, while each phase defines **how participants play** through a dedicated ruleset.

An event consists of one or more phases, allowing competitions to evolve over time with different song pools and gameplay rules.

---

## Event Types

There are three primary event types.

### IRL Tournament

A tournament played at a physical venue.

IRL tournaments use the dedicated Tournament module, which manages:

- Divisions
- Brackets
- Rounds
- Matches

Although the tournament takes place locally, matches may still be played using online lobbies.

---

### Online Tournament

A tournament played remotely.

Online tournaments use the same Tournament module as IRL tournaments, but every match is played remotely through online lobbies.

---

### Online Event

A generic online community event.

Unlike tournaments, Online Events are much more flexible and are composed of one or more phases with dedicated rulesets.

An online event exposes a descriptive format.

Examples include:

- Pack Release Events
- Community Events
- Tournament Preparation Events
- Seasonal Events

Behaviour of an event is entirely defined by the phase ruleset.
---

## Event Structure

Every event contains:

- Name
- Type
- Format (optional, descriptive)
- Start date
- End date
- One or more phases

Each phase contains:

- Start date
- End date
- Song Pool
- Ruleset

This allows events to evolve over time.

Examples:

- a Pack Release event may contain a single 48-hour phase;
- a Seasonal Event may contain one phase every month;
- a Tournament Preparation event may switch gameplay rules between phases.

---

## Song Pools

Each phase owns exactly one Song Pool.

Different phases may use different song pools.

Examples:

- qualification songs
- finals songs
- monthly pools
- pack release songs

---

## Rulesets

A Ruleset defines how a phase works.

Rulesets are implemented as application modules and determine:

- gameplay behaviour
- backend validation
- score submission rules
- leaderboard generation
- interaction with the game

Each phase uses exactly one Ruleset.

### Global Leaderboard

Players compete asynchronously on the entire Song Pool.

Results are generated from score submissions.

The leaderboard calculation itself may use different algorithms depending on the event (for example ITL or Stamina RPG).

---

### Lobby Match

Players challenge each other through online lobbies.

Gameplay is based on direct matches between participants.

Song selection is defined by the lobby match system.

---

### Sightread

Players may only submit their first attempt.

Restart is disabled inside the game.

---

### Fixed Time Set

Players must complete the Song Pool within a fixed amount of time.

The ruleset may also define a maximum allowed rest time between songs.

---

### Tournament

Uses the dedicated Tournament module.

This ruleset enables tournament-specific gameplay, such as bracket progression and tournament matches.

---

## Notes

Not every event is based on direct matches.

Some rulesets produce matches between players.

Others collect score submissions and generate leaderboards directly.
