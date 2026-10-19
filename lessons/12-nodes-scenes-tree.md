# 12 — Nodes, Scenes, and the Scene Tree

Godot games are built from **nodes** arranged into **scenes**. A node is an object with a focused responsibility: displaying a sprite, playing audio, detecting collisions, or organising other nodes. A scene is a saved arrangement of nodes that can be reused.

## The scene tree

Imagine a simple player scene:

```text
Player (CharacterBody2D)
├── Sprite2D
└── CollisionShape2D
```

The root node is `Player`. The sprite and collision shape are children. This organisation lets the player object group visual and physics-related pieces together.

## Why scenes are reusable

You might build an enemy once, save it as `Enemy.tscn`, and then instance it many times in a level. Each instance starts from the same scene structure but can have different properties.

A scene is not just a picture. It may contain nodes, attached scripts, resources, signal connections, and property values.

## Referencing child nodes

In Godot 4, a script can use an on-ready reference to a child node:

```gdscript
extends Node2D

@onready var sprite: Sprite2D = $Sprite2D

func _ready() -> void:
    sprite.visible = true
```

The path `$Sprite2D` refers to a child named `Sprite2D`. The name and path must match the scene tree. `@onready` assigns the reference when the node is ready, which is useful for child nodes that are created as part of the scene.

For more complex paths, use the scene tree to confirm the exact path. Renaming a node can break a path that depends on its old name.

## When to use which node

Choose nodes based on their job, not because one node is always best:
- `Node`: general-purpose organisation.
- `Node2D`: a 2D transform for positioned objects.
- `Sprite2D`: displays a 2D texture.
- `Area2D`: detects overlapping bodies or areas.
- `CharacterBody2D`: a character moved through physics-aware code.
- `Control`: user-interface layout and interaction.

## Practice tasks

1. Build a scene with a `Node2D` root and a `Sprite2D` child.
2. Attach a script to the root and print its name.
3. Create a separate scene for a collectible item.
4. Explain why putting a sprite and collision shape under one player root can be useful.

**Official references:** [Nodes and scenes](https://docs.godotengine.org/en/stable/getting_started/step_by_step/nodes_and_scenes.html) · [Node class](https://docs.godotengine.org/en/stable/classes/class_node.html)
