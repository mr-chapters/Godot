# SFX Makers' Book — Chapter 2: Bring Sound into Godot

> **Mission:** press Space and hear a sound effect from a running test scene.

## Organise and import
Create `audio/sfx/` in your project and put a sound file inside. Godot imports audio through its resource pipeline; allow the editor to finish importing the file before testing it. Keep filenames descriptive.

## Choose the right audio node
- `AudioStreamPlayer`: global sounds such as UI clicks or music.
- `AudioStreamPlayer2D`: sounds coming from a position in a 2D world.
- `AudioStreamPlayer3D`: sounds coming from a position in a 3D world.

A button click usually does not need to become quieter when the player moves across the map, so AudioStreamPlayer is a good default.

## Build a keyboard test
1. Create a Node2D named `SoundTest`.
2. Add an AudioStreamPlayer child named `SfxPlayer`.
3. Assign your audio file to the player's **Stream** property.
4. Attach this script to SoundTest:

```gdscript
extends Node2D

@onready var sfx_player: AudioStreamPlayer = $SfxPlayer

func _unhandled_key_input(event: InputEvent) -> void:
    if event is InputEventKey and event.pressed and not event.echo:
        if event.keycode == KEY_SPACE:
            sfx_player.play()
```

Run the scene and press Space. `@onready` stores a reference to the child after the node is ready. `$SfxPlayer` is a shorthand node path. `play()` begins playback.

This is a test harness. In a real game, call the sound when a meaningful event happens, such as a button press or item collection.

## Use actions for real controls
For a larger project, create a named action in **Project > Project Settings > Input Map**, then use that action instead of hard-coding a key. Named actions can be remapped and shared across keyboard/controller layouts.

## If there is no sound
1. Is a stream assigned?
2. Is the player node in the running scene?
3. Does the code reach `play()`?
4. Is the system volume or Master bus muted?
5. Is the sound file silent or extremely quiet?
6. Is another playback restarting the same player?
7. Did Godot import the resource successfully?

Add a temporary print immediately before `play()`. If it prints but you hear nothing, check the stream and audio output next.

## Overlapping effects
If the same AudioStreamPlayer receives another `play()` call before the sound finishes, playback can restart. This is fine for a button click but may sound wrong for many rapid pickups. Use multiple players or a pool only when your game needs overlapping playback.

## Mini-mission
Add a second AudioStreamPlayer named `ErrorPlayer` and a separate key to test a different effect.

**Boss challenge:** make three effects play for three different events and write down what should trigger each one.

## Checkpoint
1. Which node usually fits a UI click?
2. What does `@onready` do?
3. What does `play()` do?
4. Why might repeated playback restart a sound?

<details><summary>Answer key</summary>

1. AudioStreamPlayer.
2. It initializes a node reference when the node is ready.
3. Starts playback of the assigned stream.
4. The same player is being told to start again.
</details>

**Next:** [Music, loops, and a clean mix](03-music-loops-and-audio-mixing.md).
