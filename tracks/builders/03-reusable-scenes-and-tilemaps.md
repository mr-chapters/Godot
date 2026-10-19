# Builders' Book — Chapter 3: Build Once, Reuse Everywhere

> **Mission:** build a reusable coin scene and paint a small room with a tile set.

## Why reusable scenes matter

A scene can represent a coin, enemy, door, button, menu, or entire level. Once a coin scene works, you can instance it many times. Fixing the original scene can improve every instance that uses it.

A coin scene might look like:

```text
Coin (Area2D)
├── Sprite2D
└── CollisionShape2D
```

The root is an Area2D because the coin detects a body entering its area without behaving like a solid wall. Add a shape to CollisionShape2D and assign a suitable texture to Sprite2D.

Save it as `coin.tscn`. To use it in a level, drag the scene from the FileSystem dock into the viewport or use the Instantiate Child Scene button. These are instances of the reusable scene.

## Tile sets and tile maps

Tile-based levels use a collection of reusable tiles: ground, walls, water, paths, and decoration. Godot 4 uses TileMapLayer nodes for tile layers in current versions; older projects may use a TileMap node. The exact editor layout depends on your Godot 4 minor version.

A sensible layer plan:
- Ground layer: walkable floor.
- Solid layer: walls and obstacles with collision.
- Decoration layer: non-blocking details.
- Foreground layer: art that intentionally overlaps the player.

Separate layers make editing and rendering order easier to reason about. Keep collision enabled only where gameplay requires it.

## Collision authoring checklist

For every tile or object that should block movement:
1. Confirm a collision shape exists in the scene or tile data.
2. Check collision layer and mask settings.
3. Run the level and walk into it from several directions.
4. Inspect corners and narrow passages.
5. Confirm decorative art does not have accidental collision.

The visual edge and collision edge should agree closely enough that the player understands what is solid.

## Build a room from modules

Create a small kit:
- one floor tile,
- one wall tile,
- one corner,
- one door,
- one decoration.

Use a consistent grid and a consistent tile size. If your art uses 16×16 pixels, start with a 16-pixel tile grid unless the game has a clear reason to do otherwise.

Do not use dozens of tiny variations before the layout works. Build the route with a small set of pieces, play-test, then add detail.

## Lab: reusable pickup room

1. Build and save `coin.tscn`.
2. Instance six coins in a test room.
3. Change the coin's appearance once and observe how the instances update.
4. Add walls and floor using TileMapLayer or simple reusable scenes.
5. Run the scene and test every passage.

## Builder review

- Can another developer understand the scene tree?
- Are repeated objects instances rather than manually duplicated structures?
- Are node names descriptive?
- Are art and collision separated where helpful?
- Is the level still readable when zoomed out?
- Does the level run at the intended window size?

## Boss challenge

Make a reusable door scene with a visible locked/unlocked state. Create two instances in one room. Document which properties should be unique per instance and which should be shared by all doors.

## Checkpoint

1. Why make a coin a separate scene?
2. What is a TileMapLayer used for?
3. Why separate decorative tiles from solid collision?
4. What is the benefit of descriptive node names?

<details><summary>Answer key</summary>

1. To reuse and maintain it consistently.
2. Painting and organizing tiles on a 2D grid.
3. To avoid blocking movement with objects that should be decorative.
4. It makes the scene tree easier to understand and maintain.
</details>
