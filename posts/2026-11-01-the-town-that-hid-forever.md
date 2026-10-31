# The town that hid forever (and the towns that fought back)

*1 November 2026 · work in progress toward v0.10*

We built a headless **sim runner**. It runs the real town simulation outside Unity, with no graphics, about 8,000× faster than real time. Twenty different towns (seeds), three in-game days each, take about five minutes. It writes a report on who lived, who died, why, and whether the story was worth watching. This post covers what it caught. Most of it was not flattering.

## What failed
The Phase 2 gate asks for varied, explainable outcomes: not everyone dead in hour one, not everyone surviving, and outbreaks that don't just fizzle. On the v0.9 defaults:

| Gate check | v0.9 | Now |
|---|---|---|
| Not all dead in hour 1 | pass (20/20) | pass (20/20) |
| Somebody beyond patient zero is lost | **fail** (16/20) | 19/20 (see below) |
| Varied outcomes | pass (σ 19 pp) | pass (σ 35 pp) |
| Outbreak sustains past day 1 | **fail** (7/20 fizzled) | pass (5/20) |
| Not a foregone wipe | pass | pass (0/20 wiped) |

**The real problem: everyone hid, forever.** By hour one the whole town was indoors, and it stayed there for three days, in every one of the 20 towns. There was nothing to watch. The runner's new activity breakdown showed why:
- Word spreads fast: everyone was *aware* within about three hours.
- Once aware, every distant gunshot anywhere in town spiked their alarm back to maximum. With 40–80 gunshots a day, alarm never fell below about 0.6.
- At that level of alarm, "hide" beat every other choice, so half the town sat in a cupboard for 72 hours.

Fixes so far:
- **Habituation.** People who know about the dead stay *wary*, but a far-off shot no longer sends them into panic. Only something close does: a scream next door, a shot down the street, or seeing one. Their fear now settles back to a baseline wariness within hours.
- **Life goes on, differently.** Once people know, they skip most work shifts. They make supply runs, check on friends and go looking for family. Idle strolls mostly stop. Before, 45 people went to work on day two as if nothing had happened; now the streets fill with people who have a reason to be out.
- **The outbreak has more teeth.** Bites infect more often (30% → 40%). Barricades hold for 6 minutes instead of 8. Patient zero is now three dead and four bitten (was two and three), and the bitten turn spread across the first six hours instead of all at once.

**Bugs the runner found:**
- One person was spawned *inside a wall* and stood frozen for three days, asking for a path 259,000 times. Fixed: a start point that isn't walkable now falls back to their front door.
- Agents could get trapped in fenced yards with no route out (the town has 62 small walkable "islands"). The runner's pathfinder now snaps them back the way the game's NavMesh does. The game side still needs its own check.

**Still failing or not good enough:**
- One town in 20 ended up losing nobody beyond the patient zeros. We're calling this a feature (see below), but the gate counts it as a fail.
- The runner still flags "ALL_INDOORS" everywhere. That flag counts anyone inside *any* building, including people at work or on a supply run, so it no longer measures what we care about. It needs replacing with a check on whether people are moving between places.
- 5 of 20 towns still snuff the outbreak out on day one.
- It's harsh now: 13 of 20 towns end below 35% alive. That's more drama, but the curve needs watching.

## The town fights back
The living are good at killing zombies, sometimes *too* good:
- In **7 of 20 towns the living held**, ending with 77–90% alive.
- **In every town that held, every zombie that rose was put down.** Seed 18: 8 rose, 8 destroyed. Seed 15: 14 rose, 14 destroyed. Patient zero walks out at dawn, a cop or a veteran with a gun hears the screaming, and it ends there.
- Across all 20 towns, **275 of the 843 people who rose were put down again** by the living (33%). On v0.9, when the outbreak rarely got going, it was 53%.
- Gunfire is the town's weapon and its curse: towns that held fired 20–55 shots. Every shot is heard 120 m away, and the dead come to it.
- The falls are interesting too. Seed 20 lost its first barricade 64 times on day one: one bad street, and the dead got into house after house. Seed 14 held for two days, then collapsed on day three (43 breaches in a single day).

**Who lived longer** (all towns pooled, versus a 48% average): bartenders +8 pp, office workers +7 pp, security guards +5 pp. Retirees (−11 pp) and truck drivers (−9 pp) fared worst. Police officers were slightly *below* average (−2 pp): they go toward the screaming.

**What causes the losses now:** being bitten at a breached door (36%), being mauled while already infected (20%), being bitten when someone inside turned (15%), and being bitten in the open (13%). Patient zeros are now only 16% of losses (they were 33%), so the town's own choices drive the story.

## Also coming in v0.10
- **Sound.** Wind, birdsong by day that thins as the town dies, crickets at night, gunshots echoing between houses, breaking glass, banging doors, crashes, engines on passing cars, wailing car alarms, and the subject's heartbeat when you ride their eyes. Each sound is synthesised for now, and ElevenLabs versions follow once generated. There's a volume control in the pause menu.
- **The dead look dead.** There's no zombie animation pack yet, so zombies get a procedural posture on top of the walk cycle: a hunched spine, a lolling head, arms that hang or reach out once they've seen prey. Each one is a little different.

## Next
I'll keep re-running the runner after every balance change and posting the numbers here, failures included.
