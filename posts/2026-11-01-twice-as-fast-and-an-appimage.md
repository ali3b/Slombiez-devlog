# Twice as fast, and one file for the Deck

*1 November 2026 · v0.9.0-alpha*

## Steam Deck AppImage
Every release now ships a single-file **AppImage** for the Deck. Download it, tick "Is executable", and add it to Steam as a Non-Steam game. No unpacking. It's built from the official AppImage runtime with a compressed squashfs of the game: about 90 MB.

## Finding the slowdown
v0.8 regressed: the Deck tier fell from ~140 fps to ~70 fps at 4× speed. The investigation went like this:
- **Character views off:** back to 142 fps, so it was the characters.
- **The simulation, timed system by system:** about 1 ms per tick for the whole town, so not the sim.
- **Ground lookups:** every visible character queried the NavMesh for its ground height on every tick, which is thousands of queries per second at 4×. The fix moved the work into the bake: heights are now refined against the NavMesh detail mesh once, and the runtime just reads an array.
- **Animators:** every character was running Synty's full four-layer locomotion controller (head-look, body-look and lean layers, dozens of states) to do one thing: walk at a given speed. It's now a purpose-built one-layer blend tree: idle → walk → run → sprint.

**Result:** the worst case (the whole town turned, 75 zombies on screen, 4× speed) went from **57 fps to 111 fps** on the Deck tier, with zero hitches.

## Bodies that match
While building the new controllers, we checked every Sidekick body by eye. People now get a body that matches their sex, and women walk with Synty's feminine animation set.

## Next
The balance pass is up next: the headless runner's report is coming in, and early signs say too many families escape by car in the first hour.
