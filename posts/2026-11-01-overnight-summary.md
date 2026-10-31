# Overnight: v0.10 → v0.16 in one page

*1 November 2026 · for when you wake up*

Seven releases while you slept. Each came with a Steam Deck AppImage, a Deck tarball and a PC Ultra build, each was soak-tested before publishing, and all are on the private releases page. **Latest: v0.16.0-alpha.**

## What you can do now that you couldn't last night
| | Where | How |
|---|---|---|
| **Become anyone** and survive as them | v0.11 | inspect someone → **D-pad ▲ / K**, or **Start → Become someone** |
| **Whisper** a thought into anyone's head | v0.12 | inspect → **D-pad ▼ / T** |
| Whisper **in your own words** | v0.12 | first item in the whisper menu (keyboard) |
| Whisper to **the dead** (home, loved ones, places) | v0.13 | inspect a zombie → **D-pad ▼** |
| **Save / Load** the whole town exactly | v0.12 | Start menu |
| See **their story** and **arcs to their family** | v0.14 | just inspect someone |
| **Weather**: misty mornings, foggy dusks, rain | v0.15 | it simply happens |
| An **inner voice** for whoever you inspect (optional) | v0.13 | drop `llm.secrets.json` next to the game (see README.txt) |

## The town behaves better
- **Nobody emigrates in five minutes.** Leaving town by car went from 16% of the town (mostly in the first hours) to about 8–11%, spread over days.
- **A believable start.** The night's dead rise *at home* among their families, and one walks the street. If you haven't been told, a walking corpse at a distance is "a man walking funny" until you get a good look.
- **Police hesitate** before shooting someone who was a neighbour this morning.
- **Outbreaks don't fizzle.** All five Phase 2 gate checks pass with traffic and survival fully simulated (they were failing two of five before).
- **Survivors live their lives:** needs, scavenging, barricades, regrouping in daylight, and looking before they go out.
- **The dead make sound:** groans, moans, snarls and fists on doors (synthesised until the voices are generated).

## Failures caught and fixed (all documented in the posts)
- The whole town hiding forever (v0.10).
- Cars leaving town in the first minutes (v0.11).
- A 100 ms hitch on the first groan (v0.12.1).
- A feed crash *inside the simulation step*, caught by the release gate before it shipped (v0.15). The UI can no longer break the world's tick.
- Parched survivors walking straight into the dead (v0.16).

## Numbers
- **Steam Deck tier:** 157–167 fps at 4× speed with 0 hitches in every release. A **26-game-hour** test at 16× speed averaged 165 fps with 0 errors.
- **Automated tests:** 117 → 162.
- **Headless runner:** now simulates traffic, survival and weather; 20 towns × 3 days in about 5 minutes.

## Needs you
- **Mall and Office scenarios** need the POLYGON Shops / Office packs imported. I didn't import anything while you slept.
- **Voices:** set an ElevenLabs key (env `ELEVENLABS_API_KEY`) and run `Tools/voices/generate_voices.py`. It now generates the ambience and sound effects too.
- **Optional language model** for minds: `llm.secrets.json` next to the game (Anthropic, OpenRouter or a local server).
