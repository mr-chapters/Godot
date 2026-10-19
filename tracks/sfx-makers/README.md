# 🔊 SFX Maker Track — Make Your Game Sound Alive

**Role:** create or choose sounds that help players feel actions and understand feedback.

Sound effects can make a tiny pixel game feel responsive. Your first goal is not to make hundreds of sounds. It is to make a few useful sounds that are clear, comfortable, and consistent.

## Level 1 — Make your first sound
Read the [audio and sound design manual](../../manual/audio/README.md).

Free or accessible starting tools:
- [ChipTone](https://sfbgames.itch.io/chiptone) — create retro-style sound effects.
- [jsfxr](https://sfxr.me/) — generate arcade-inspired effects in a browser.
- [Audacity](https://www.audacityteam.org/) — trim, fade, and edit audio.
- [Kenney audio assets](https://kenney.nl/assets) — find ready-made game audio packs.

Always check the current licence of the exact asset before using or sharing it.

## Level 2 — Create a tiny sound pack
Make or source:
1. UI click
2. UI confirm
3. UI error
4. player jump
5. landing
6. item pickup
7. damage feedback
8. level complete
9. ambient loop

Use clear file names such as `ui_click.wav` and `item_pickup.wav`. Keep a record of each file's source and licence.

## Level 3 — Put sound into Godot
Follow [Import and play audio](../../manual/audio/04-import-and-play-audio.md).

Learn the difference between:
- `AudioStreamPlayer` — UI, music, and non-positional sounds;
- `AudioStreamPlayer2D` — sounds positioned in a 2D world;
- `AudioStreamPlayer3D` — sounds positioned in a 3D world.

Learn how to route sounds to Music, SFX, UI, and Ambience buses using the [audio mixing guide](../../manual/audio/06-audio-buses-and-mixing.md).

## Sound design tips

- Short sounds are often better for actions that repeat frequently.
- A sound should confirm an action, not delay it.
- Keep music quieter than important gameplay cues.
- Test sound effects while other sounds are playing.
- Make sure the game is still understandable when muted.
- Don't use copyrighted music or sound effects without permission.

## Boss challenge

Make a complete audio set for a 30-second pixel game. Include a menu click, jump, pickup, hit, victory sound, and looping music. Give players separate music and effects volume controls.

**Bonus:** make two variations of the pickup sound so collecting many items does not sound exactly the same each time.
