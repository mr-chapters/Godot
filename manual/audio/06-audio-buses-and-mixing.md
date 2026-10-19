# 06 — Audio Buses, Volume, and Mixing

An audio bus is a route through which sound travels before reaching the output. Buses make it possible to adjust groups of sounds together and apply audio effects.

## A practical bus layout

Open the **Audio** panel at the bottom of the Godot editor. Create buses such as:

- `Master` — the final output.
- `Music` — background tracks.
- `SFX` — gameplay sound effects.
- `UI` — menu and interface sounds.
- `Ambience` — environmental layers.

Route the extra buses to Master. Assign each AudioStreamPlayer's **Bus** property to the appropriate bus name. Names must match; if a bus name does not exist, a player can fall back to Master.

## Decibels

Audio volume uses decibels (dB). Values below zero reduce level; `0 dB` is the reference level for the signal at that point in the digital audio chain. Avoid pushing the final mix into clipping.

Use your ears as well as meters. Make important effects audible without making repeated sounds uncomfortable. Check the mix through ordinary speakers or headphones at a comfortable volume.

## Volume settings in code

```gdscript
extends Node

func set_bus_volume(bus_name: StringName, linear_value: float) -> void:
    var bus_index := AudioServer.get_bus_index(bus_name)
    if bus_index == -1:
        push_warning("Audio bus not found: " + String(bus_name))
        return

    var safe_value := clampf(linear_value, 0.0, 1.0)
    AudioServer.set_bus_volume_db(
        bus_index,
        linear_to_db(maxf(safe_value, 0.0001))
    )
```

This function expects a linear value from 0.0 to 1.0, checks that the bus exists, and converts the value to decibels. The small minimum avoids trying to convert exact zero to a decibel value; for a true mute control, use the bus's mute property instead.

## Effects

Godot buses can use audio effects. Depending on your needs, effects can shape tone, space, dynamics, or distortion. Add effects sparingly and compare the result with the unprocessed sound.

## Mixing checklist

- [ ] Music, UI, and effects can be adjusted independently.
- [ ] The master output does not audibly clip.
- [ ] Important cues remain clear while music is playing.
- [ ] Repeated sounds are not excessively loud or tiring.
- [ ] Mute and volume settings work as expected.

**Official reference:** [Audio buses](https://docs.godotengine.org/en/stable/tutorials/audio/audio_buses.html)
