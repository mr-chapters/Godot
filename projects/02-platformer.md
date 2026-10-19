# Project 02 — 2D Platformer

Build a small side-view platform game. The player should run, jump, land on platforms, avoid hazards, and reach an exit.

## Requirements

- A `CharacterBody2D` player with collision.
- Horizontal movement and jump input.
- Gravity applied during physics processing.
- Several platforms.
- At least one hazard.
- A finish area that changes the game state or opens a win screen.
- A restart path after failure or completion.

## Important concepts

Use the built-in `is_on_floor()` method to check whether a CharacterBody2D is on the floor after movement. Apply gravity when the character is not on the floor. Use `move_and_slide()` to move and resolve sliding collisions.

A minimal movement starting point:

```gdscript
extends CharacterBody2D

@export var move_speed: float = 240.0
@export var jump_velocity: float = -380.0
@export var gravity: float = 980.0

func _physics_process(delta: float) -> void:
    if not is_on_floor():
        velocity.y += gravity * delta

    var direction := Input.get_axis("move_left", "move_right")
    velocity.x = direction * move_speed

    if Input.is_action_just_pressed("jump") and is_on_floor():
        velocity.y = jump_velocity

    move_and_slide()
```

Create the `move_left`, `move_right`, and `jump` actions in Project Settings → Input Map. Tune gravity and jump velocity through testing; the values here are starting points, not universal physics settings.

## Build order

1. Test horizontal movement on a flat floor.
2. Add gravity and floor collision.
3. Add jumping and prevent repeated mid-air jumps.
4. Build a level with multiple platforms.
5. Add hazards and a clear failure response.
6. Add an exit area and win state.
7. Test edge cases such as jumping against walls and falling off the level.

## Stretch challenges

- Add a double jump with a clearly defined reset rule.
- Add moving platforms.
- Add checkpoints.
- Add animations that respond to movement.
- Add a simple level selection screen.

## Completion checklist

- [ ] Movement and jumping feel predictable.
- [ ] The player cannot jump indefinitely unless that is intentional.
- [ ] Platforms and hazards have appropriate collision shapes.
- [ ] Win and failure states both work.
- [ ] The level can be restarted.
- [ ] You tested the game after changing the physics values.

**Official reference:** [2D movement](https://docs.godotengine.org/en/stable/tutorials/2d/2d_movement.html)
