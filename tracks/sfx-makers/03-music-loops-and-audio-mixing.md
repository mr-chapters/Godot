# SFX Makers' Book — Chapter 3: Music, Loops, and a Clean Mix

> **Mission:** make music and effects coexist without drowning each other out.

## SFX versus music

Sound effects communicate immediate actions. Music shapes mood over a longer period. They need different priorities: a pickup effect should be audible over the music, but it should not be painfully loud.

## Make a loop feel intentional

A loop repeats without an obvious unwanted gap or click. To create one:
1. Choose a musical phrase that can repeat.
2. Trim it at a musically sensible boundary.
3. Listen across the join several times.
4. Check for clicks caused by a sudden waveform jump.
5. Export and test the loop in the game, not only in your audio editor.

A seamless loop does not always need to fade out. A fade can hide an edit, but it may also create a quiet gap if applied to a section meant to repeat continuously.

## Audio buses in Godot

Open the Audio panel and use buses such as **Master**, **Music**, and **SFX**. Route music players to Music and effect players to SFX. Then adjust the bus levels independently.

A bus is a shared processing and volume route. It lets you lower music without lowering UI sounds, or mute sound effects while leaving music active.

You can set a player's `bus` property in the Inspector. The bus name must match a bus in the project.

## Simple audio manager example

For a small project, place an AudioStreamPlayer in a node called AudioManager, assign the music stream, and set its Bus to Music. This example assumes the Music bus exists:

```gdscript
extends Node

@onready var music_player: AudioStreamPlayer = $MusicPlayer

func play_music() -> void:
    if not music_player.playing:
        music_player.play()

func stop_music() -> void:
    music_player.stop()
```

If the manager must survive scene changes, it can be configured as an Autoload singleton in Project Settings. Use an Autoload only when global lifetime is useful; a small game may not need one.

## Loudness and fatigue

Avoid simply turning every sound up. If the mix feels crowded:
- lower music when important effects occur,
- shorten effects that linger,
- remove unnecessary layers,
- leave space for dialogue or warnings,
- test through laptop speakers and headphones when possible.

Do not trust only your headphones at maximum volume. Listen at a comfortable level and use a reference sound or known good mix to compare.

## Lab

1. Create Music and SFX buses.
2. Route a music player to Music.
3. Route your coin and jump effects to SFX.
4. Test lowering each bus separately.
5. Make a looping music file and listen to at least five loop boundaries.

## Boss challenge

Create two moods—calm exploration and danger. Plan which sounds change, how the transition happens, and how the player can still hear critical warning effects.

## Checkpoint

1. Why separate music and SFX buses?
2. What can cause a click at a loop boundary?
3. Why test a loop repeatedly?
4. What should remain audible when a mix becomes busy?

<details><summary>Answer key</summary>

1. Independent volume and processing control.
2. An abrupt waveform discontinuity or a badly placed edit.
3. Repetition exposes gaps, clicks, and tiring patterns.
4. Important gameplay feedback and warnings.
</details>
