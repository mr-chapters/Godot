# 🧱 Builder Track — Build Worlds Players Want to Explore

**Role:** assemble scenes, environments, levels, and spaces where the gameplay happens.

Builders are not "just placing objects." Strong level design teaches the player where to go, creates interesting choices, and makes movement and goals easy to read.

## Level 1 — Understand the editor
Start with [installing Godot and exploring the editor](../../lessons/01-install-godot.md) and [nodes and scenes](../../lessons/12-nodes-scenes-tree.md).

Learn:
- the Scene dock and FileSystem dock;
- parent and child nodes;
- transforms, position, rotation, and scale;
- saving a scene and setting the main scene;
- instancing a reusable scene into a level.

**Mini-mission:** make a room from reusable wall, floor, and decoration scenes.

## Level 2 — Build a playable 2D level
Read [input and movement](../../lessons/14-input-and-movement.md) and [collision and Area2D](../../lessons/16-collision-and-area2d.md).

Learn:
- static collision for walls and floors;
- collision shapes that fit the visible object;
- triggers for doors, pickups, and exits;
- tile-based layouts and TileMap/TileMapLayer features appropriate to your Godot version;
- clear paths, landmarks, safe areas, and obstacles.

**Mini-mission:** build a small maze with a key, locked door, and exit trigger.

## Level 3 — Make a level readable
- Put the goal where players can understand it.
- Use visual contrast to separate walkable space from hazards.
- Introduce one new mechanic at a time.
- Use repeated visual patterns to teach what objects do.
- Test collision at corners, ledges, and narrow passages.
- Keep decoration from obscuring important gameplay information.

**Mini-mission:** create an easy first level that teaches one mechanic without a wall of instructions.

## Level 4 — Polish and performance
- Reuse scenes rather than manually duplicating complex node trees.
- Keep node hierarchies understandable.
- Avoid excessive real-time lights and effects if they hurt performance.
- Check navigation and collision in the running game, not just the editor.
- Test at the intended window size and aspect ratio.

## Boss challenge

Build a small platforming level with a starting point, three challenges, a checkpoint, one collectible, and an exit. Ask a friend to play without explaining the route. Watch where they get confused and improve the layout.

**Bonus:** create two different routes: one safe and one more difficult with an optional reward.
