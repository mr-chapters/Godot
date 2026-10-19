# Pixel Artists' Book — Chapter 4: Polish, Consistency, and Delivery

> **Mission:** prepare a small set of game art that another teammate can import without chasing missing files or guessing dimensions.

## 1. Polish is consistency

A polished sprite set does not mean every asset has maximum detail. It means assets follow the same visual rules. Check:
- outline thickness,
- palette and contrast,
- light direction,
- perspective,
- pixel density,
- animation timing,
- scale relative to the player.

If one object uses soft gradients while the rest use crisp pixel clusters, decide whether the difference is intentional.

## 2. Check art in the game, not only in the art editor

Import your assets into a real level. Look at them:
- at normal gameplay size,
- while moving,
- against the intended background,
- beside other sprites,
- under lighting or effects,
- at the smallest supported viewport.

Art can look excellent zoomed in and become unreadable at game scale. The actual game is the final judge.

## 3. File handoff

A tidy handoff contains:
- exported assets,
- editable source files when appropriate,
- animation names and frame dimensions,
- tile size and grid notes,
- palette or art-direction notes,
- asset source and licence details for third-party content.

Avoid filenames such as `final_final_new.png`. Use names that describe the asset and state.

## 4. Performance and file size

Large textures consume memory. Do not export every tiny sprite on a massive canvas. Crop transparent space where appropriate, use sensible texture sizes, and follow the project's import settings. Optimisation should preserve visual quality and be based on the target platform.

## 5. Boss challenge

Prepare a character, idle and walk animations, a small tileset, and a background. Write a short handoff note explaining frame sizes, palette rules, filenames, and any external asset licences. Import the set into Godot and fix any problems you discover.

## Checkpoint

1. Why inspect art at gameplay size?
2. What should a handoff note contain?
3. Why use descriptive filenames?
4. Why should texture optimisation consider target hardware?

<details><summary>Answer key</summary>

1. Small details and contrast can behave differently at normal scale.
2. Dimensions, animation names, palette rules, file organisation, sources, and licences.
3. They make assets easier to find and maintain.
4. Memory and performance differ by platform.
</details>
