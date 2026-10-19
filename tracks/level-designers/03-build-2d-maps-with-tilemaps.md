# Chapter 3 — Build 2D Maps with TileMaps

**Mission:** build a reusable 2D environment using tiles, layers, and collision.

## 1. Understand the pieces

A tileset is a collection of reusable tile graphics and their properties. A TileMapLayer places tiles on a grid. Multiple layers let you separate ground, walls, decoration, and collision-relevant objects.

In Godot 4, the modern workflow uses **TileMapLayer** nodes. Older tutorials may show a single TileMap node; the editor workflow can differ between Godot versions, so check which version the project uses.

## 2. Prepare the tileset

Use consistent tile dimensions and a clear visual style. Import the texture, create a TileSet resource, define the tile regions, and configure physics layers/shapes for solid tiles. Test collisions in a running scene; visible walls do not automatically block the player unless collision is configured.

## 3. Organise layers

A simple setup might be:
- Ground: floor tiles.
- Obstacles: walls and objects that block movement.
- Decoration: grass, cracks, and small visual details.
- Foreground: art that intentionally overlaps the player.

Keep the node tree understandable. Do not create dozens of layers unless they solve a real problem.

## 4. Terrain and autotiling

Terrain tools can automatically choose matching tile edges and corners. They reduce repetitive placement but need correct terrain connections and tile definitions. Always inspect corners and transitions after painting.

## 5. Collision checklist

- Is each solid tile's collision shape configured?
- Can the player move through intended doorways?
- Are decorative tiles accidentally blocking movement?
- Are narrow gaps wide enough for the player's collision shape?
- Do the tile visuals line up with collision?

## Mini-mission

Create a small room with a floor, solid boundary walls, a doorway, one decorative layer, and a collectible. Ensure the player cannot walk through the walls.

## Checkpoint

- What is the difference between a TileSet and TileMapLayer?
- Why separate decoration from solid geometry?
- Why test the collision in-game?

**Boss challenge:** create a small dungeon room kit with at least four floor tiles, four wall/corner variants, and one readable exit. Test the room with the player controller.

**Diagram — simple 2D layer stack**

~~~text
Foreground decoration   (may overlap player)
Decorations             (visual only)
Obstacles / walls       (solid collision)
Ground                  (walkable floor)
----------------------
Player and gameplay run above these layers
~~~

**Further reading:** [TileMapLayer](https://docs.godotengine.org/en/stable/classes/class_tilemaplayer.html) and [Using TileMaps](https://docs.godotengine.org/en/stable/tutorials/2d/using_tilemaps.html).
