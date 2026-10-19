# 05 — Music, Loops, and Ambience

Music and ambience create atmosphere, but they should support gameplay rather than compete with it.

## Choose a role for each track

- **Menu music:** establishes the game's identity and should work while the player waits.
- **Gameplay music:** supports the pace and mood of the main loop.
- **Victory or completion cue:** gives a clear sense of resolution.
- **Ambience:** creates a sense of place, such as wind, rain, or a quiet room.

Start with one track and one ambience layer. Add more only when they improve the experience.

## Make a seamless loop

1. Choose a section that can repeat musically.
2. Avoid a sudden difference in loudness between the end and beginning.
3. Export the loop and test it repeatedly.
4. Import it into Godot and enable looping using the resource or import options available in your version.
5. Test the loop in-game, not only in an audio editor.

A loop can be technically seamless but still sound musically awkward. Listen for rhythm, harmony, and background noise at the join.

## Switch tracks

For a small project, use separate AudioStreamPlayer nodes for menu and gameplay music. When changing scenes, decide whether the music should continue or restart. If it should continue, keep the music player in a persistent scene or use an autoload music manager.

## Avoid overwhelming the mix

Music should not drown out important feedback sounds. Lower the music bus when needed, keep sound effects readable, and let players adjust music and effects independently.

## Practice

1. Create a short music loop.
2. Add a separate ambience track and set a sensible level.
3. Switch from menu music to gameplay music.
4. Test the transition and fix any abrupt cut.
5. Add a settings control to adjust music volume.

**Official reference:** [Audio streams](https://docs.godotengine.org/en/stable/tutorials/audio/audio_streams.html)
