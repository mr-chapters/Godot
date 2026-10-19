# SFX Makers' Book — Chapter 1: Sound Design from Zero

> **Mission:** design three sounds that clearly communicate a coin pickup, a jump, and a mistake.

## What does an SFX maker do?
A sound-effects maker helps players understand and feel events through audio. A bright coin sound can say “reward collected.” A low thud can make an object feel heavy. A short warning sound can ask for attention.

Good sound design is not just loudness. It combines duration, pitch, texture, timing, and context.

## Learn the shape of a sound
A common way to describe a sound's envelope is:
- **Attack:** how quickly it begins.
- **Decay:** how it falls from its initial peak.
- **Sustain:** how it continues.
- **Release:** how it fades away.

A coin pickup often uses a quick attack and short decay. A power-up might use a bright attack with a longer tail. A heavy door might combine a low impact with a creak.

## Useful tools
- [ChipTone](https://sfbgames.itch.io/chiptone) — create retro-style effects.
- [jsfxr](https://sfxr.me/) — generate arcade-inspired sounds.
- [Audacity](https://www.audacityteam.org/) — trim and edit audio.
- [Kenney assets](https://kenney.nl/assets) — ready-made game audio packs.
- [OpenGameArt](https://opengameart.org/) and [Freesound](https://freesound.org/) — community audio libraries.

Always check the licence for the exact file you use. “Free to download” does not automatically mean “free for every use.”

## Plan a sound palette

| Event | Feeling | Design idea |
|---|---|---|
| Coin pickup | Bright and rewarding | Short high-pitched blip or two-note sparkle |
| Jump | Light and responsive | Quick upward sweep |
| Damage | Clear but not irritating | Short lower tone with a soft noisy edge |

Related events should sound like they belong to the same game. Rare rewards can be a more special variation of the ordinary pickup sound.

## Listen like a designer
Ask:
- Can I identify the event without looking?
- Does the sound finish before the next likely event?
- Is it pleasant when repeated twenty times?
- Does it compete with music or dialogue?
- Is there unwanted silence or clipping?
- Does it sound too much like another important event?

Test the sound in the game. A sound that works once may become irritating when repeated.

## First sound pack
Create `audio/sfx/` and export `coin_pickup.wav`, `player_jump.wav`, and `damage_hit.wav`. Keep the editable source files too. WAV is convenient for short lossless effects; choose formats based on the target and use case.

## Mini-mission
Make normal and rare coin sounds that share a style but feel different.

**Boss challenge:** listen to the pickup sound repeated for thirty seconds. If it becomes tiring, shorten it, soften sharp frequencies, or remove layers.

## Checkpoint
1. What is the attack of a sound?
2. Why test sounds repeatedly?
3. Why check an asset licence?
4. Why should related sounds share a style?

<details><summary>Answer key</summary>

1. How quickly it begins and reaches its initial level.
2. Repetition reveals fatigue, overlap, and irritating details.
3. It determines how the asset may be used and whether attribution is needed.
4. It makes the audio palette feel consistent.
</details>

**Next:** [Bring sound into Godot](02-import-and-play-audio.md).
