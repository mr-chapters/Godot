# SFX Makers' Book — Chapter 5: Positional Audio and Immersive Worlds

> **Mission:** make a sound feel like it comes from a place in the game world.

## 1. Global versus positional sound

A UI click should sound the same wherever the player is. A waterfall, enemy, or door should sound as if it exists at a position in the world.

In Godot:
- `AudioStreamPlayer` is for non-positional sound.
- `AudioStreamPlayer2D` is for 2D positional sound.
- `AudioStreamPlayer3D` is for 3D positional sound.

Positional audio may change volume and, depending on settings, stereo position as the listener moves.

## 2. Make the sound source meaningful

Place an AudioStreamPlayer2D near the object that makes the sound. Assign a stream and test how it behaves as the player moves toward and away from it. Adjust attenuation and distance settings in the Inspector for your game's scale.

Do not use positional audio for every effect. If a tiny UI sound becomes quiet when the player walks to the other side of the map, the sound node is probably in the wrong role.

## 3. Avoid audio clutter

Several nearby sounds can overlap into noise. Choose which sounds should be continuous, which should play once, and which should have variations. Ambience can establish a place; small effects should mark important events.

Consider:
- whether a sound should repeat,
- whether multiple copies can play at once,
- whether it needs a cooldown,
- whether it should stop when the source disappears,
- whether it should be quieter than the player's own actions.

## 4. Audio perspective in 3D

A 3D sound's perceived distance depends on the listener, source position, attenuation settings, and audio setup. Make sure the active audio listener follows the player or camera as intended. Test at close, medium, and far distances rather than setting values by guesswork alone.

## 5. Lab

Build a simple 2D room with a looping ambient source in one corner and a pickup effect that plays at the pickup location. Walk around the room and listen to how each behaves. Keep the UI click global.

## 6. Boss challenge

Design a short audio scene with one global UI sound, one positional environmental loop, and one positional one-shot. Test whether players can tell which sound is near and which is part of the interface.

## Checkpoint

1. Which node is suitable for a UI click?
2. Why use positional audio for a waterfall?
3. What causes audio clutter?
4. Why test at multiple distances?

<details><summary>Answer key</summary>

1. AudioStreamPlayer.
2. The sound should appear to originate from the waterfall's world position.
3. Too many overlapping or overly loud sounds competing for attention.
4. To tune how volume and spatial perception change with distance.
</details>
