# Scripters' Book — Chapter 4: Make Things Respond

> **Mission:** move a character with keyboard input, then understand how signals let game objects communicate.

## Input actions first

Open **Project > Project Settings > Input Map**. Add an action named `move_right` and assign the Right Arrow and D keys. Add `move_left` with Left Arrow and A. Add `move_up` and `move_down` too.

Actions are better than hard-coding keys because players can rebind controls and you can support more devices later.

## A simple 2D movement script

Create a `CharacterBody2D` with a child `Sprite2D` or other visible graphic and a `CollisionShape2D`. Attach:

```gdscript
extends CharacterBody2D

@export var speed: float = 220.0

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

`@export` makes speed editable in the Inspector. `Input.get_vector()` combines four actions into a direction vector and limits diagonal movement so it is not faster than straight movement. `_physics_process()` runs on the physics tick. `move_and_slide()` moves a CharacterBody2D using its velocity and handles sliding along collisions.

The four action names must match the Input Map exactly. If your project uses different names, change the script or the actions to match.

## Why physics process?

Movement and physics are generally handled in `_physics_process()`, which runs at a fixed physics cadence. `_process()` runs each rendered frame and is useful for many visual updates. Use the callback that fits the job; do not assume every task belongs in one loop.

## Signals: announcements between nodes

A signal is an event announcement. A button can announce that it was pressed; a pickup can announce that it was collected; a health component can announce that health changed.

Example custom signal:

```gdscript
extends Node

signal health_changed(new_health: int)

var health: int = 100

func take_damage(amount: int) -> void:
    health = max(health - amount, 0)
    health_changed.emit(health)
```

Another node can connect to `health_changed` and update a HUD. This reduces tight coupling: the health component does not need to know which exact label displays the number.

In the editor, select a node, open the **Node** dock, choose a signal, and connect it to a receiver. You can also connect signals in code. Always confirm the receiver method's arguments match the signal.

## Lab

1. Make a CharacterBody2D move using the actions above.
2. Create a health component or simple Node script that emits `health_changed`.
3. Connect the signal to a method that prints the new health.
4. Call `take_damage(10)` and observe the result.

## Common bugs

- **No movement:** Input Map names differ from code, the script is not attached, or the wrong scene is running.
- **Character passes through everything:** check collision shape, physics body type, and collision layers/masks.
- **Diagonal movement is faster:** normalize the direction; `Input.get_vector()` already handles this.
- **Signal method never runs:** check that the signal is connected and the event is actually emitted.
- **Invalid argument error:** compare the signal's argument list with the receiver method.

## Boss challenge

Create a character that moves, receives damage through a function, and reports health changes through a signal. Do not make the health component directly update a specific UI label.

## Checkpoint

1. Why use Input Map actions?
2. What is the difference between `_process` and `_physics_process`?
3. What does a signal communicate?
4. Why is `max(health - amount, 0)` useful?

<details><summary>Answer key</summary>

1. Controls can be remapped and reused consistently.
2. Render-frame updates versus fixed-step physics updates.
3. That an event occurred, optionally with data.
4. It prevents health from dropping below zero in this example.
</details>
