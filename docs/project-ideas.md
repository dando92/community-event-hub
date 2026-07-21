# Project Ideas

> [Home](../README.md)

## External Applications

Community Event Hub should not directly manage every possible event format.

Dedicated external applications may manage tournaments, seasonal events, lobby matches, pack releases, and other community activities.

This model would allow the hub to:

* integrate events and management tools that already exist
* allow community developers to create new event formats
* distribute development, hosting, and maintenance
* avoid centralizing every feature in a single project

External applications would manage their own rules and publish the relevant final data to Community Event Hub through shared APIs.

## Event Integration

An event managed by an external application would also be registered in Community Event Hub.

The hub and the external application would keep their own identifiers and link the two event representations.

The external application would manage the event while it is active and publish its final data once the event is completed.

The publishing APIs may accept:

* event information
* participants
* song pools
* final standings
* leaderboard results
* direct match results
* historical chart usage

## Result Models

Events may publish results using two main models.

### Leaderboard Results

Leaderboard results represent an ordered classification of participants.

This model may be used by seasonal events, fixed-time events, pack release events, and other asynchronous competitions.

### Direct Match Results

Direct match results represent competition between specific participants.

This model may be used by IRL tournaments, online tournaments, and lobby match events.

An event may publish direct match results together with its final standings.

## Official Circuit and Rankings

All events may publish and preserve their results in Community Event Hub.

Only events recognized as part of the official circuit should affect the shared global ranking.

Unofficial events would still contribute to the historical archive without changing player ratings.

Event results and the global ranking should remain separate concepts.

## Historical Chart Data

Community Event Hub may preserve how charts were used during events, including:

* charts included in song pools
* charts played
* player picks
* chart bans
* random selections

This data could be used to create dashboards for chart artists and show how their charts are selected and played across community events.

## Community Collaboration

The project is intended to be developed with the community.

The current goals are to understand:

* whether organizers would use the hub
* whether existing projects could integrate with it
* whether developers are interested in creating external applications
* which historical data would be valuable to players and chart artists
