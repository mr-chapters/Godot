# 16 — Collision Detection and Area2D

Collision systems help game objects detect walls, platforms, hazards, pickups, and other bodies. In Godot, a node's collision behaviour depends on its class and setup.

## Collision shapes

A physics body or area usually needs a `CollisionShape2D` or `CollisionPolygon2D` child. Select the collision shape node and assign a shape resource such as `RectangleShape2D` or `CircleShape2D`.

The visual sprite does not automatically become a collision shape. Collision geometry is configured separately.

## What is Area2D?

`Area2D` detects when physics bodies or other areas enter, exit, or overlap it. It is useful for triggers, pickups, damage zones, and detection ranges. It generally does not physically push bodies away like a solid physics body.

## Collectible example

Create an `Area2D` scene with a `CollisionShape2D` child and a visual child such as `Sprite2D`. Ensure the collision shape is assigned. Attach this script to the Area2D:

```gdscript
extends Area2D

signal collected

func _ready() -> void:
    body_entered.connect(_on_body_entered)

func _on_body_entered(body: Node2D) -> void:
    if body.is_in_group("player"):
        collected.emit()
        queue_free()
```

Add your player node to a group named `player` using the Node dock's **Groups** section, or adapt the check to your own player identification system.

When a matching body enters, the collectible emits a signal and queues itself for deletion. `queue_free()` safely schedules the node to be removed at the end of the current frame.

## Collision layers and masks

- **Collision layer:** which categories an object belongs to.
- **Collision mask:** which categories an object checks for collisions with.

A collision shape alone is not enough if layers, masks, monitoring, or object types are configured incorrectly. Debug by checking all of these settings.

## Practice tasks

1. Make a collectible disappear when the player enters it.
2. Add a second group, such as `enemy`, and make the collectible ignore enemies.
3. Build a hazard Area2D that emits a `damaged` signal.
4. Test with collision layer/mask settings and explain what changed.

**Official references:** [2D physics introduction](https://docs.godotengine.org/en/stable/tutorials/physics/physics_introduction.html) · [Area2D](https://docs.godotengine.org/en/stable/classes/class_area2d.html)
