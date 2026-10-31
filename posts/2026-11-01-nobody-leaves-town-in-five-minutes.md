# Nobody leaves town in five minutes any more

*1 November 2026 · in progress toward v0.11*

While playing survival I watched three families **drive out of town by 08:05**, five minutes into day one, before anything had really happened. So the headless runner now simulates traffic too: the town's own 29 vehicles, baked from the scene. That let us measure it properly.

## What was wrong (measured over 20 towns × 3 days)
- **16% of the whole town left by car**, and most of them in the first hours.
- **The whole town "knew" within five minutes.** At 08:05, 50 of 71 people were already *aware*. Three patient zeros were walking among 38 people out on a morning stroll, and anyone who glimpsed one at 30 m instantly understood that the dead walk. Town panic hit 0.53 by 08:05.
- **Two hidden shortcuts out of town:**
  - Someone walking to their car for an errand who then got scared got a "leave town forever" route the moment they reached the car. It skipped the decision entirely.
  - Every car-owning household re-rolled "should we run for it?" every few minutes. Over a day the dice say yes for nearly all of them.

## The fixes
- **Recognition.** If you haven't been told, the first walking corpse you see is just a stranger: *"Is he drunk? He's walking funny."* Up close (under about 7 m), or seeing it go for someone, it's unmistakable. At a distance it takes a long look, about 45 seconds at 30 m. And some people go over to help: *"Ellen doesn't look right. I'm going over."* That's how the first bites happen.
- **Leaving town is a real decision.** It's made once, it sticks for hours, and it only becomes likely once the *whole town* is panicking. Someone fleeing who reaches a car now drives to safety somewhere in town instead of emigrating.
- **Households decide about once a day** whether to pack the car. About one in five do, and they leave over the next few hours.

## Results
| | Before | After |
|---|---|---|
| Left town by car | 16.3% | **8.0%** |
| Left in the first hour | 66 people (10 towns) | 10 people (20 towns) |
| Departures spread over | mostly the first hours | first hours 30%, day 2+ 42% |
| Aware by 08:15 | 54 | 29 |

## What failed
- **Outbreak sustains: FAIL, 6/20 towns fizzled on day one** (it was 4/20). With fewer people fleeing, more stay to fight, and in six towns the patient zeros are put down before anyone else is bitten. It's the town being good at killing zombies again: 217 of 650 risen (33%) were put down. I'll tune this next.
- Daytime life is a median 9% of the living out doing something. Watchable, but quiet in towns that are falling.

## Tests
All 144 automated tests pass, survival included.
