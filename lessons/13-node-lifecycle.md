# 13 — The Node Lifecycle and Frame Updates

Godot calls certain methods at particular moments in a node's life. Understanding these callbacks helps you decide where setup and gameplay logic belongs.

## `_ready()`

Godot calls `_ready()` after the node and its children have entered the scene tree and are ready. It is commonly used to initialise values, connect signals, or obtain references to child nodes.

```gdscript
extends Node

func _ready() -> void:
    print("This node is ready.")
```

## `_process(delta)`

Godot calls `_process(delta)` each rendered frame when processing is enabled. The `delta` argument is the elapsed time in seconds since the previous process frame.

```gdscript
extends Node2D

var rotation_speed: float = 1.0

func _process(delta: float) -> void:
    rotation += rotation_speed * delta
```

Multiplying a rate by `delta` makes the change depend on elapsed time rather than assuming every computer draws the same number of frames per second.

## `_physics_process(delta)`

Use `_physics_process(delta)` for code that should run on the physics tick, such as many character movement calculations. Physics processing uses a fixed timestep by default, which helps physics behaviour stay consistent.

```gdscript
extends CharacterBody2D

@export var speed: float = 240.0

func _physics_process(_delta: float) -> void:
    velocity.x = speed
    move_and_slide()
```

This minimal example moves right continuously. It is for demonstrating the callback, not a finished player controller.

## Choosing the callback

- Initialise references and starting state in `_ready()`.
- Use `_process(delta)` for frame-based presentation logic when appropriate.
- Use `_physics_process(delta)` for physics-related movement and calculations.
- Do not place expensive work in every frame unless it is genuinely needed.

## Practice tasks

1. Print a message from `_ready()`.
2. Rotate a `Node2D` slowly using `delta`.
3. Explain why a movement rate multiplied by `delta` behaves differently from adding a fixed amount every frame.
4. Move physics code into `_physics_process` and test the result.

**Official reference:** [Idle and physics processing](https://docs.godotengine.org/en/stable/tutorials/scripting/idle_and_physics_processing.html)
