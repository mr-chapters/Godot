# Chapter 4 — Lighting, Cameras, and Composition

**Mission:** guide attention and make a 3D scene easy to read during gameplay.

## Lighting is communication

Lighting can establish mood, separate foreground from background, and guide players toward a goal. It can also hide hazards or flatten important shapes. Build lighting for gameplay readability first, then style.

Start with a clear main light, enough fill or environmental light to keep important forms readable, contrast between interactable objects and surroundings, and a test under the darkest and brightest conditions the player can encounter.

## Camera choice changes the experience

Perspective cameras make distant objects appear smaller; orthographic cameras keep apparent size more consistent. A close camera can make a prop feel huge, while a distant camera can hide its detail. Test models from the actual player camera rather than judging only in the editor viewport.

## Composition and focal points

A focal point is where the viewer's attention lands first. Use contrast, placement, shape, and light to support the gameplay goal. Avoid putting every bright colour and strongest contrast in the same place. Hazards, doors, pickups, and enemies should be distinguishable.

## Performance-aware lighting

Real-time shadows and many dynamic lights can cost performance. Use only effects that improve the scene. Profile the game on target hardware; do not assume editor performance represents every player's device.

## Mini-mission

Build a small room with a doorway, a collectible, and a hazard. Make the collectible easy to spot without making the hazard invisible. Test from the gameplay camera.

## Checkpoint

- How can lighting support gameplay?
- When might an orthographic camera be useful?
- Why test on target hardware?

**Boss challenge:** make a tiny scene with one clear destination and two optional points of interest. Ask another person what they notice first, then adjust the composition.

**Further reading:** [Godot 3D lighting](https://docs.godotengine.org/en/stable/tutorials/3d/lights_and_shadows.html) and [Camera3D](https://docs.godotengine.org/en/stable/classes/class_camera3d.html).
