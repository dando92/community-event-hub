# Event Formats

> [Home](../README.md)

## Event Types

There are three primary event types.

### IRL Tournament

A tournament played at a physical venue.

The tournament structure is managed by a dedicated Tournament application, which may handle:

* divisions
* brackets
* rounds
* matches
* qualifications
* song selection
* tournament progression

Community Event Hub stores the tournament as an event and preserves its shared data, participants, final results, and references to the external Tournament application.

---

### Online Tournament

A tournament played remotely.

Online tournaments may use the same dedicated Tournament application as IRL tournaments, but their matches are played remotely through online lobbies.

Community Event Hub stores the tournament as an event and preserves its shared data, participants, match results, final standings, and references to the external Tournament application.

---

### Online Event

A generic online community event.

Online events are flexible and may represent many different kinds of activities.

Examples include:

* Pack Release Events
* Community Events
* Tournament Preparation Events
* Seasonal Events, such as ITL and Stamina RPG

Each online event is managed by an external application dedicated to its specific format or ruleset.

The external application determines how the event works, including any phases, song pools, score submissions, restrictions, or leaderboard calculations.

Community Event Hub stores the shared event information and preserves the results produced by that application.

---

## Event Structure

Every event stored in Community Event Hub contains shared information such as:

* name
* type
* format and descriptive information
* start date
* end date
* participants
* song pools, when required to preserve historical chart data
* external application reference
* final or published results
* event status

The exact internal structure of an event is not defined by Community Event Hub.

For example, an external application may organize an event as:

* multiple monthly phases with a sequence of changing song pools
* a tournament with brackets and matches
* a fixed-time event in which players have 48 hours to play a specific set of charts

These details belong to the external application and do not need to be represented as common entities inside the hub.

---

## Event Formats and Rulesets

Events may produce two main types of results:

* leaderboard results, mainly used by events such as ITL and Stamina RPG
* direct match results, mainly used by tournaments and online lobby matches

The external application is responsible for applying the event rules and publishing results in the format expected by Community Event Hub.

### Seasonal Events

Players compete asynchronously on a set of charts.

The external application manages score submissions and calculates the final leaderboard.

Events such as ITL and Stamina RPG may use different leaderboard calculation algorithms.

Community Event Hub stores the published event leaderboard and the related historical data.

---

### Lobby Match

Players are given a specific time window in which they can challenge each other through online lobbies.

This format may encourage greater use of online lobbies, which are currently underused.

The external application manages:

* lobby creation
* participants
* match scheduling
* song selection
* direct matches
* match results

The application may support multiple song-selection methods.

Examples include:

* **Random selection**, where songs are automatically selected from an eligible pool
* **Player picks**, where each player chooses one or more songs
* **Draft selection**, where a predefined set of songs is generated and players remove or ban songs before the match

Draft rules may define:

* the number of songs initially selected
* the number of bans available to each player
* the order in which players ban songs
* the criteria used to determine the first player
* the number of songs that remain available for the match

The selected songs may be sent directly to the game lobby by the external application.

Song-selection data is operational and may remain temporary. However, Community Event Hub could preserve the charts that were actually played, picked, or banned.

Community Event Hub stores the results of each match.

---

### Fixed Time Set

Players must complete a set of charts within a fixed time window.

The external application may also define:

* a maximum rest time between songs
* the order of the charts
* allowed retries
* score submission deadlines

Sightread events may disable the restart functionality and only accept the player's first attempt.

This format is particularly suitable for pack release events. Chart artists can create an event in which they release a limited number of charts to be played within a fixed time window, allowing players to challenge each other on those charts.

Community Event Hub stores the published event leaderboard and the related historical data.

---

### Tournament

The dedicated Tournament application manages tournament-specific concepts such as:

* divisions
* brackets
* rounds
* matches
* qualifications
* tournament progression

Community Event Hub stores the results of each match, the final standings, and any other relevant historical data published by the Tournament application.

---

## Historical Data

Community Event Hub maintains the historical archive for community events.

Every external application publishes event data using a defined integration format.

Once the relevant information is published or finalized, the hub preserves data such as:

* event metadata
* participants
* played songs or charts
* final standings
* match results, when relevant
* leaderboard results, when relevant
* ranking updates
* references to the originating external application

The hub does not need to preserve every temporary state used internally by an external application.
