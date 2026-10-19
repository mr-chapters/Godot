# 03 — Make Sounds for Pixel and Retro-Inspired Games

You can make useful retro-style effects without recording a real instrument. The key is to choose a sound shape and timing that fit the event.

## Method A: use a sound generator

1. Open [ChipTone](https://sfbgames.itch.io/chiptone) or [jsfxr](https://sfxr.me/).
2. Choose a category close to the event, such as pickup, jump, hit, or laser-like game effect.
3. Generate several variations.
4. Listen at a comfortable volume and choose the clearest one.
5. Shorten the effect if it delays the action or becomes annoying when repeated.
6. Export WAV when available.
7. Name it descriptively, such as `player_jump.wav`.
8. Import it into Godot and test it during actual gameplay.

Treat generator presets as starting points. Change pitch, duration, tone, and envelope so different events do not all sound identical.

## Method B: edit an existing recording

1. Open the file in Audacity.
2. Select the useful portion and trim unnecessary silence.
3. Add a short fade-in or fade-out if the sound clicks at its edges.
4. Adjust loudness without causing clipping.
5. Export to a format suitable for the sound.
6. Listen to the exported file, not just the editor preview.

Always keep an unedited original if you may need to change the edit later.

## Design recipes

These are creative starting points rather than exact technical presets:

- **Pickup:** a brief bright tone, often rising in pitch.
- **Jump:** a quick upward movement with a short duration.
- **Landing:** a lower, softer impact, adjusted to match the character's size.
- **Menu click:** a very short, quiet tick that does not become tiring.
- **Error:** a brief downward or dissonant cue, kept comfortable to hear.
- **Victory:** a small sequence of notes or a clear rising cue.
- **Damage feedback:** a short, distinct sound that remains readable alongside visuals.

## Avoid repetitive sound fatigue

If a sound plays on every step or every repeated action, it can become irritating. Consider using multiple variations, reducing the volume, or only playing it for meaningful events. Do not layer many loud effects at the same time.

## Export and organise

A simple folder structure:

```text
res://
└── audio/
    ├── music/
    ├── ambience/
    ├── ui/
    └── sfx/
        ├── player/
        ├── items/
        └── environment/
```

For short sound effects, WAV is a straightforward choice. Compressed formats such as Ogg Vorbis can be useful for music and longer ambience. Test the actual exported build because import settings and platform behaviour may differ.
