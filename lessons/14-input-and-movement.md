# 14 — Input and Player Movement

Movement connects input, vectors, physics, and the scene tree. This lesson uses Godot 4's `CharacterBody2D`.

## Prepare the scene

Create a scene with a `CharacterBody2D` root. Add a `Sprite2D` and a `CollisionShape2D` as children. Assign a texture and a suitable shape if you want to see and collide with the player.

Open **Project → Project Settings → Input Map**. Add actions named `move_left`, `move_right`, `move_up`, and `move_down`. Bind them to A/D/W/S or the arrow keys.

## Movement script

Attach this script to the `CharacterBody2D` root:

```gdscript
extends CharacterBody2D

@export var speed: float = 240.0

func _physics_process(_delta: float) -> void:
    var direction := Input.get_vector(
        "move_left",
        "move_right",
        "move_up",
        "move_down"
    )
    velocity = direction * speed
    move_and_slide()
```

## How it works

1. `Input.get_vector` reads four named actions and returns a 2D direction.
2. The vector points in the chosen direction. When there is no input, it is `Vector2.ZERO`.
3. Multiplying by `speed` converts a direction into a velocity measured in pixels per second in a typical 2D setup.
4. `velocity` is the built-in movement velocity used by `CharacterBody2D`.
5. `move_and_slide()` moves the body and handles sliding along collision surfaces.

The action names in code must exactly match the Input Map. If you do not create the actions, the input will not work as expected.

## Why vectors matter

A `Vector2` has an x and y component. For example, `Vector2(1, 0)` points right and `Vector2(0, -1)` points up in Godot's usual 2D coordinate system. `Input.get_vector` also limits diagonal input so moving diagonally is not unintentionally faster.

## Practice tasks

1. Change the speed in the Inspector using the exported variable.
2. Add a sprint action and make the player move faster while it is pressed.
3. Add a boundary or wall and test how collision affects movement.
4. Explain why `move_and_slide()` is appropriate here instead of directly changing the position every frame.

**Official references:** [2D movement overview](https://docs.godotengine.org/en/stable/tutorials/2d/2d_movement.html) · [CharacterBody2D](https://docs.godotengine.org/en/stable/classes/class_characterbody2d.html) · [Input](https://docs.godotengine.org/en/stable/classes/class_input.html)
