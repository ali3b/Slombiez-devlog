# Changelog

## v0.16.0-alpha (2026-11-01)
- Survivors look before they go (wait for a clear street unless desperate)
- Event bus isolates UI/audio/camera listeners: a bug there can't break the sim tick
- Director cam: whispers, barricades, starvation
- Long soak: 26 game hours at 16x, 165 fps, 0 errors; release soak Deck 157 fps, 0 hitches

## v0.15.0-alpha (2026-11-01)
- Weather: misty mornings, foggy dusks, rain; changes sight and sound outdoors; fog, grey light, rain visuals and audio; feed lines
- Fix: feed crash inside the sim step (sighting merged into a bite line); feed can no longer break a tick
- Deck 159 fps, 0 hitches; 160 tests

## v0.14.0-alpha (2026-11-01)
- Inspector: Their story (past + today's moments); fits 720p/Deck (two-column needs)
- Relationship arcs to loved ones (alive / risen / dead)
- First-run hints
- Deck 167 fps, 0 hitches; 16x stress 175 fps

## v0.13.0-alpha (2026-11-01)
- Whispers to the dead: stir them home, toward someone they loved, or to places that meant something
- Regroup: survivors alone make a daylight dash to bigger groups (daytime life in falling towns 3% -> 6%)
- Optional language model (Anthropic / OpenRouter / local): deeper typed whispers, inner voice for the inspected person; offline fallback always
- Deck 163 fps, 0 hitches; 157 tests

## v0.12.1-alpha (2026-11-01)
- Fix: 100 ms hitch on the first groan or gunshot (sounds now synthesised while loading); 0 hitches on both tiers

## v0.12.0-alpha (2026-11-01)
- Whispers: D-pad down / T on anyone; thoughts that fit them; they react as themselves; accepted thoughts change behaviour
- Whisper in your own words (offline parser into the same safe effects)
- Save / Load (exact, including traffic and decay)
- Zombie voices: synthesised groans, far moans, snarls, door pounding

## v0.11.0-alpha (2026-11-01)
- Survival mode begins: become anyone (D-pad up / K, or Start > Become someone); move, run, sneak, fight, search, go in and out, shoot, board up, eat and drink, take all; carry on as a loved one after death
- Needs, loot, scavenging, barricades and real weapons for the whole town; the inspector shows needs and kit
- Recognition: a distant walking corpse is "a man walking funny" until a good look
- The night's dead rise at home among family; police hesitate before shooting
- Leaving town by car: 16% -> 8-11%, spread over days; bus and garbage truck run until true panic
- Headless runner simulates traffic and survival; all Phase 2 gate checks pass
- Deck tier soak: 164 fps avg, p99 13.2 ms, 0 hitches; Ultra 1080p 82 fps

## v0.10.0-alpha (2026-11-01)
- Headless sim runner: 20 towns x 3 days in ~5 min; balance report with failures documented
- Fix: the whole town hid forever (noise habituation; aware people make supply runs instead of working)
- Tougher outbreak: 3 dead + 4 bitten, bites infect 40%, barricades hold 6 min
- Fix: a person spawned inside a wall stood frozen for 3 days
- Soundscape (ambience, gunshots, glass, doors, crashes, engines, alarms, POV heartbeat) and volume setting
- Zombies hunch, loll and reach (procedural posture)
- Deck tier soak: 181 fps avg, p99 12.6 ms; Ultra 1080p: 91 fps

## v0.9.0-alpha (2026-11-01)
- Steam Deck AppImage
- Worst-case crowd performance 57 -> 111 fps (lightweight locomotion, baked exact heights)
- Sex-matched bodies and feminine animation set

## v0.8.0-alpha (2026-11-01)
- Traffic on an auto-extracted road network with the town's own 29 vehicles: commuters, bus, garbage truck; panic, crashes, alarms, abandonment, fleeing town
- Town decay rendered with POLYGON Apocalypse props
- Feed: traffic events; repeated bites fold into one line

## v0.7.0-alpha (2026-10-31)
- Pause menu (D-pad): graphics tier live, speed, New town, controls, quit
- Sheltering people are drawn inside their rooms (revealed by the roof cutaway)

## v0.6.0-alpha (2026-10-31)
- Death replay: rewind anyone's last minute through their eyes
- Street lamps at night (emissive heads + camera-following spotlights)
- Fixed red-tinted nights (demo scene grading stacked on ours)

## v0.5.0-alpha (2026-10-31)
- Through-their-eyes POV for the living (fear, wounds, fever) and the dead (noise rings, fragments)
- Director camera that finds and captions the most dramatic moment
- Release tooling: both flavours soak-tested from the package before publishing

## v0.4.0-alpha (2026-10-31)
- Intro cinematic that finds a real patient zero and lets you watch them rise
- Two build flavours: **Steam Deck** and **PC Ultra** (4K shadow maps, SSAO, MSAA, cinematic post-processing)
- Voice system: generic ElevenLabs voices for reactions (silent until the voice library is generated)

## v0.3.0-alpha (2026-10-31)
- Observer UI: inspect anyone (who they are, what they're doing and why, thoughts, their people), live event feed, follow camera
- Minds only know what they've seen: ordinary-life thoughts until someone sees the dead; fever reads as flu

## v0.2.0-alpha (2026-10-31)
- 75 living townspeople with daily routines; patient-zero outbreak; bites, incubation, turning in their own bodies
- Curiosity spreads it; only seeing the dead causes panic
- Personality-driven hordes; zombies drift to old homes, work and loved ones
- 9 → 229 fps (Sidekick bone compaction)

## v0.1.0-alpha (2026-10-31)
- First Steam Deck build: the town's real population, all turned (the "zombie ant farm")
