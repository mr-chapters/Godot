# Pixel Artists' Book — Chapter 2: Animate and Export Your Art

> **Mission:** create a tiny idle animation and bring it into Godot without blurry pixels.

## Plan frames around motion

A sprite sheet stores multiple frames in one image. Each frame should use the same cell dimensions so the engine can select them consistently. Keep the character aligned to a stable pivot or baseline where possible; otherwise the sprite may appear to jump around during animation.

For a two-frame idle:
1. Frame 1: relaxed pose.
2. Frame 2: small head or body movement.
3. Preview at a low frame rate.
4. Check whether the motion feels intentional rather than twitchy.

Animation does not need many frames. A clear change between a few poses can be more effective than a large sheet full of nearly identical frames.

## Export cleanly

- Use transparent PNG for sprite sheets with empty background.
- Avoid accidental semi-transparent pixels around crisp pixel-art edges unless intentional.
- Keep frame size and sheet layout documented.
- Store editable source files separately from exports.
- Use descriptive names such as `hero_idle.png` and `hero_walk.png`.

## Animate with AnimatedSprite2D

In Godot, create an AnimatedSprite2D and a SpriteFrames resource. Add an animation named `idle`, add the frames, and set its speed and looping option in the editor.

To play it:

```gdscript
extends Node2D

@onready var sprite: AnimatedSprite2D = $AnimatedSprite2D

func _ready() -> void:
    sprite.play("idle")
```

The node path must match your scene tree and the animation name must match the name in SpriteFrames.

## Pixel-perfect presentation

Pixel art often benefits from nearest-neighbour filtering. Inspect the texture's import settings and the node or project texture-filtering settings available in your Godot version. Test at the actual game resolution.

Integer scaling (2×, 3×, 4×) generally preserves uniform pixel blocks better than arbitrary fractional scaling. If your viewport is stretched to fit different screens, choose the stretch settings deliberately and test common window sizes.

## Animation review

- Does the character's feet stay on a believable baseline?
- Do body parts flicker because their outlines change accidentally?
- Is the animation readable at normal speed?
- Does the first frame match the final frame for a smooth loop?
- Does the sprite still read against the game's background?

## Boss challenge

Create idle, walk, and damage animations for the same character. Use a consistent palette and silhouette. Document frame size, frame count, and intended playback speed.

## Checkpoint

1. Why should sprite-sheet cells have consistent dimensions?
2. What does nearest-neighbour filtering help preserve?
3. Why keep source art files?
4. What should you inspect at normal game size?

<details><summary>Answer key</summary>

1. So frames can be selected and aligned predictably.
2. Crisp pixel edges.
3. So art can be revised later.
4. Readability, animation, scaling, and contrast.
</details>
