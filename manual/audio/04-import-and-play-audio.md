# 04 — Import and Play Audio in Godot 4

Godot imports audio files as audio resources. You can assign them in the Inspector or load them through scripts.

## Step 1: import a file

1. Copy a sound file into your project's `audio/` folder.
2. Wait for Godot to import it.
3. Select the file in the FileSystem dock and review its Import settings if needed.
4. Reimport after changing import options.

Do not rename or move resource files casually after scripts begin referring to their paths. Use Godot's FileSystem dock when possible so references can be updated.

## Step 2: play a non-positional sound

Add an `AudioStreamPlayer` node to your scene and name it `PickupSound`. Assign your pickup audio file to its **Stream** property. Attach a script to the parent node:

```gdscript
extends Node

@onready var pickup_sound: AudioStreamPlayer = $PickupSound

func play_pickup_sound() -> void:
    pickup_sound.play()
```

Call `play_pickup_sound()` when an item is collected. The node must exist in the scene and its name must match the script's path.

`AudioStreamPlayer` is appropriate for menus, UI, and sounds that do not need to appear at a position in the game world.

## Step 3: play a sound at a 2D world position

Use `AudioStreamPlayer2D` for sounds that should feel located in the 2D world. Add it to an appropriate scene, assign a stream, and call `play()` when the event occurs. Its volume and panning depend on the listener/camera and configured audio properties.

For a 3D world, use `AudioStreamPlayer3D`.

## Play a sound from a reusable scene

A simple approach is to put an `AudioStreamPlayer` in the player, item, or UI scene that owns the event. This keeps the sound close to the behaviour that triggers it. For frequently repeated effects, test whether the node's polyphony settings allow the sound to overlap as intended.

## Play background music

Add an `AudioStreamPlayer` to a persistent music node, assign the music stream, enable looping in the resource/import settings where available, and call `play()`. Make sure the loop point does not create an obvious pause or click.

## Common problems

- **No sound:** check the stream assignment, master volume, audio device, mute state, and whether `play()` is called.
- **Wrong node path:** verify the exact name and location of the AudioStreamPlayer.
- **Sound plays only once:** check whether the event runs again and whether the node is stopped or freed.
- **3D sound is too quiet:** inspect distance attenuation and listener setup.
- **Web build behaves differently:** test in the browser and consult the official web-audio notes for your Godot version.

**Official references:** [Audio streams](https://docs.godotengine.org/en/stable/tutorials/audio/audio_streams.html) · [AudioStreamPlayer](https://docs.godotengine.org/en/stable/classes/class_audiostreamplayer.html)
