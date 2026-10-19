# Builders' Book — Chapter 4: Lighting, Atmosphere, and Performance

> **Mission:** create two moods in the same room using composition and lighting, then keep the scene running smoothly.

## 1. Mood begins with composition

Before adding effects, decide what the player should notice. Use:
- **Scale:** large shapes can feel powerful or threatening.
- **Spacing:** tight spaces can feel tense; open spaces can feel calm.
- **Contrast:** strong contrast attracts attention.
- **Colour grouping:** related colours help areas feel connected.
- **Landmarks:** memorable shapes help players navigate.

Do not make every area equally dramatic. A quiet space gives the next dramatic space more impact.

## 2. 2D lighting in Godot

Godot 2D projects can use nodes such as PointLight2D and DirectionalLight2D with compatible CanvasItem materials and textures. A PointLight2D needs a suitable light texture. A CanvasModulate can tint the overall 2D scene.

Exact properties and editor labels vary by Godot 4 version. Start with one light and test it in a running scene before adding many overlapping lights.

## 3. Atmosphere without clutter

Try one change at a time:
1. Set a base background colour.
2. Add one focal light.
3. Use a restrained palette for the area.
4. Add limited particles or animation only if they support the mood.
5. Check whether the player, route, hazards, and pickups remain readable.

Atmosphere should not make the game's important information invisible.

## 4. Performance basics

A scene can become expensive if it contains excessive particles, many overlapping lights, huge textures, or too many active nodes. Do not optimize based on fear alone: profile and test the actual game.

Good habits:
- reuse scenes and assets where appropriate,
- avoid unnecessarily huge textures,
- limit effects that do not contribute much,
- use simple collision where possible,
- test on the weakest target device you plan to support.

## 5. Level performance test

Compare the same room with effects off and on. Watch frame pacing, visual clarity, and how it behaves on target hardware. If performance drops, disable effects one at a time to identify the expensive part.

## 6. Boss challenge

Make a calm version and a danger version of one room using lighting and colour, but keep the path and hazards easy to identify. Then test performance and readability at the actual game resolution.

## Checkpoint

1. Why should lighting support gameplay readability?
2. Why profile before optimizing?
3. Name two potential performance costs.
4. Why test on target hardware?

<details><summary>Answer key</summary>

1. The player must still see important objects and routes.
2. It identifies real bottlenecks instead of guessing.
3. Excessive particles, overlapping lights, huge textures, or many active nodes.
4. Performance differs between devices.
</details>
