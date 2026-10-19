# Builders' Book — Chapter 1: Build Your First Game Room

> **Mission:** create a simple room with a floor, walls, a player placeholder, and a camera.

## What does a builder do?
Builders arrange spaces so players understand where to go, what is dangerous, and what is worth exploring. Good building is not only decoration: the layout and collision must support the gameplay.

Godot uses:
- **Node:** one building block with a purpose.
- **Scene:** a saved arrangement of nodes that can be reused.
- **Scene tree:** the parent-child structure of a scene.
- **Inspector:** the selected node's properties.
- **Transform:** position, rotation, and scale.

## Make a room
1. Create a Godot 4 project and a 2D Scene named `Level01`.
2. Save it as `level_01.tscn`.
3. Add a `Node2D` child called `Environment`.
4. Add a `StaticBody2D` under Environment named `Floor`.
5. Add a `CollisionShape2D` under Floor and assign a RectangleShape2D. Resize the shape to form a wide floor.
6. Give the floor a visible representation too: for example, use a Sprite2D with a texture or a simple polygon. Collision shapes are for physics, not finished artwork.
7. Add a `CharacterBody2D` named `Player`. Add a CollisionShape2D with a capsule or rectangle and a Sprite2D or Polygon2D as a visible placeholder.
8. Add a `Camera2D` as a child of Player and make it the active camera using the options available in your Godot 4 version.
9. Save and run the scene with F6.

Your scene tree should be understandable:

```text
Level01 (Node2D)
├── Environment (Node2D)
│   └── Floor (StaticBody2D)
│       └── CollisionShape2D
└── Player (CharacterBody2D)
    ├── Sprite2D
    ├── CollisionShape2D
    └── Camera2D
```

## Parent and child transforms
A child follows its parent's transform. When the Player moves, the Camera2D moves with it. If the camera is a sibling of Player, it will not automatically follow the player's movement.

## Greyboxing: test before decorating
Greyboxing means using plain shapes to test a level's layout before making final art. Ask:
- Is the goal obvious?
- Is there enough room to move?
- Can the player tell floor from hazard?
- Does the camera show important information?
- Does decoration obscure a path?

## Collision is not appearance
A Sprite2D draws an image. A CollisionShape2D defines the physical area used by a physics body or area. The visual and collision shapes should agree closely enough that the player understands what is solid.

## Common mistakes
- **Player falls through floor:** check that the floor has a shape assigned and collision layers/masks allow interaction.
- **Invisible floor:** collision is invisible in normal gameplay; add a visual node.
- **Camera does not follow:** make it a child of Player and check its enabled/active state.
- **Scene will not run:** save the scene and set a main scene, or run the current scene.

## Mini-mission
Build a room with one spawn area, a floor, two walls, a goal marker, and one decoration that does not block movement.

**Boss challenge:** make a corridor guide attention toward an exit using shape, colour, and spacing without adding a giant arrow.

## Checkpoint
1. What is a scene?
2. What is the difference between Sprite2D and CollisionShape2D?
3. Why is greyboxing useful?
4. Why place Camera2D under Player?

<details><summary>Answer key</summary>

1. A saved arrangement of nodes.
2. One draws an image; the other defines a physics shape.
3. It tests layout and gameplay before expensive art work.
4. The camera follows the player's transform.
</details>

**Next:** [Make the level fair and readable](02-collision-layout-and-player-flow.md).
