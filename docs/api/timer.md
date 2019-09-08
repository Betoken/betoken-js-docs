# betoken.timer
Provides info regarding Betoken's investment cycle.

## `betoken.timer.timeTillPhaseEnd()`
### Returns
`Number`: the time left until the end of the current investment phase, in seconds.

## `betoken.timer.phase()`
### Returns
`Number`: the id of the current investment phase:
- 0 for the Intermission phase
- 1 for the Manage phase

## `betoken.timer.phaseStartTime()`
### Returns
`Number`: the Unix timestamp at which the current investment phase began, in seconds.

## `betoken.timer.phaseLengths()`
### Returns
`Array<Number>`: the lengths of the investment phases, in seconds, indexed by the phases' ids (see `betoken.timer.phase()`)

## `betoken.timer.cycle()`
### Returns
`Number`: the current cycle number.