# Domain Model

> [Home](../README.md)

## Overview

The Community Event Hub is built around the concept of an **Event**.

An Event represents a complete community initiative. It may include preparation activities, challenges, qualifications and tournaments under the same name.

The way participants play is defined separately for each phase of the Event.

```text
Event
 ├── Participants
 └── Phases
      ├── Song Pool
      └── Ruleset
```

---

## Event

An Event represents an organized community activity.

It includes:

* a name;
* a description;
* a start date;
* an end date;
* one or more phases;
* its participants.

An Event does not have a fixed format.

Its structure and behaviour are determined by the phases it contains.

For example, the same Event may include:

1. a preparation phase;
2. a qualification;
3. a final tournament.

---

## Participant

A Participant is a user registered for an Event.

Participation belongs to the Event as a whole, allowing the user to take part in its different phases.

Some specialized modules may introduce additional concepts. For example, the Tournament module may represent tournament participants as Entrants.

---

## Event Phase

A Phase represents a distinct period or activity within an Event.

Examples include:

* a monthly stage;
* a pack release window;
* a preparation period;
* a qualification;
* a fixed-time challenge;
* a tournament.

Each phase has:

* a name;
* an optional description;
* a start and end;
* one Song Pool;
* one Ruleset.

Different phases of the same Event may use different rulesets.

A phase may have a scheduled duration or may be moved forward manually by the organizers.

---

## Song Pool

A Song Pool contains the charts available during a phase.

Each phase has one Song Pool.

Different phases may use different pools.

How the charts are played depends on the phase Ruleset.

---

## Ruleset

A Ruleset defines how a phase works.

It determines:

* how participants play;
* how scores are submitted;
* how results are calculated;
* whether the phase produces matches, a leaderboard or another specialized experience.

Each Ruleset has its own dedicated management.

Current rulesets include:

* Global Leaderboard;
* Lobby Match;
* Sightread;
* Fixed Time Set;
* Tournament.

---

## Global Leaderboard

Participants play the charts in the phase Song Pool and submit their scores asynchronously.

The phase produces a leaderboard from those submissions.

Different events may calculate leaderboard points differently(ITL and SRPG), even when they use the same general format.

---

## Lobby Match

Participants challenge each other through online lobbies.

The phase produces direct matches between players.

Leaderboard is based on accumulated points over win matches.

---

## Sightread

Participants may submit only their first attempt on each chart.

Restart is disabled in game during that attempt.

This ruleset can be used, for example, for a Pack Release Event.

---

## Fixed Time Set

Participants must complete a set of charts within a limited session.

The rules may also define a maximum amount of rest time.

---

## Tournament

The Tournament ruleset use the already implemented Tournament Manager(still under development).

---

## Match

A Match represents direct competition between participants.

Matches exist only in rulesets that require them, such as:

* Lobby Match;
* Tournament.

---

## Score Submission

A Score Submission represents a participant's result on a chart.

The active Ruleset determines:

* which submissions are accepted;
* whether the first or best score is used;
* how the submission contributes to the final result.

---

## Leaderboard

A Leaderboard represents the ordered results of a phase.

It may be calculated from:

* score submissions;
* aggregated song results;
* matches;
* ruleset-specific point systems.

The calculation method belongs to the Ruleset.
