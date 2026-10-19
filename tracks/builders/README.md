# 🧱 Builders' Book — Build Worlds Players Want to Explore

**Who this book is for:** level builders, environment artists, and anyone who assembles the spaces where gameplay happens. Building is both technical and creative: collision must work, but the route must also make sense.

## Table of contents

1. [Build Your First Game Room](01-scenes-nodes-and-the-first-room.md) — nodes, scenes, parent-child relationships, collision, and greyboxing.
2. [Make the Level Fair and Readable](02-collision-layout-and-player-flow.md) — visual hierarchy, collision layers/masks, route planning, and fairness.
3. [Build Once, Reuse Everywhere](03-reusable-scenes-and-tilemaps.md) — reusable scenes, tile layers, modular kits, and collision testing.
4. [Lighting, Atmosphere, and Performance](04-lighting-atmosphere-and-optimization.md) — composition, 2D lighting, visual clarity, and profiling.
5. [Routes, Checkpoints, and Level Flow](05-level-design-and-checkpoints.md) — teach/test/reward pacing, optional routes, and recovery.

## Suggested practice order
1. Make one room with placeholder shapes.
2. Test movement and collision before decoration.
3. Turn repeated objects into reusable scenes.
4. Add one landmark, one reward, and one exit.
5. Ask someone else to play without instructions.
6. Improve the level based on what you observe.

## Builder's checklist
- [ ] The scene tree is readable.
- [ ] Solid visuals have appropriate collision.
- [ ] Decorative visuals do not accidentally block movement.
- [ ] The player can identify the goal and hazards.
- [ ] The camera shows the information needed to make decisions.
- [ ] Checkpoints are fair and consistent.
- [ ] Lighting and effects preserve readability.
- [ ] The level is tested at its actual window size.

## Further learning
- [Godot: 2D game](https://docs.godotengine.org/en/stable/tutorials/2d/index.html)
- [Godot: TileMaps](https://docs.godotengine.org/en/stable/tutorials/2d/using_tilemaps.html)
- [Godot: physics introduction](https://docs.godotengine.org/en/stable/tutorials/physics/physics_introduction.html)
- [Main GDScript course](../../README.md)

**Graduation challenge:** build a compact level with a safe start, three challenges, a checkpoint, an optional reward, and a clear exit. Have another person play it and revise the layout from their feedback.
