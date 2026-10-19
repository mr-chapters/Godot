# Chapter 8 — State Machines: Make Behaviour Predictable

**Mission:** organise behaviour that changes over time, such as a player being idle, running, hurt, or defeated.

## Why states help

A state is the current mode of an object. Without explicit states, a character might accept movement input while stunned, attack while defeated, or play conflicting animations. A state machine asks: what state am I in, and which transitions are allowed?

## Start with an enum

~~~gdscript
extends CharacterBody2D

enum PlayerState { IDLE, RUNNING, HURT, DEFEATED }

@export var move_speed: float = 220.0
var state: PlayerState = PlayerState.IDLE

func _physics_process(_delta: float) -> void:
    if state == PlayerState.DEFEATED or state == PlayerState.HURT:
        velocity = Vector2.ZERO
        move_and_slide()
        return

    var direction := Input.get_vector(
        "move_left", "move_right", "move_up", "move_down"
    )

    if direction == Vector2.ZERO:
        state = PlayerState.IDLE
    else:
        state = PlayerState.RUNNING

    velocity = direction * move_speed
    move_and_slide()

func defeat() -> void:
    state = PlayerState.DEFEATED
    velocity = Vector2.ZERO
~~~

Create the four movement actions in Project Settings > Input Map before testing. This example demonstrates a small state model; it does not implement timed hurt recovery or animation transitions.

## Plan transitions before coding

| Current state | Event | Next state |
|---|---|---|
| IDLE | movement input | RUNNING |
| RUNNING | no movement | IDLE |
| IDLE or RUNNING | takes damage | HURT |
| HURT | recovery finishes | IDLE |
| Any active state | health reaches zero | DEFEATED |

A transition table exposes missing cases before they become bugs. Decide what happens if the player receives damage while already hurt or if a pause menu opens during defeat.

## When should states become separate scripts?

One enum and a few conditions are fine for a small character. If every state needs its own timer, animation, entry/exit rules, and transitions, consider separate state scripts or a dedicated state-machine node. Do not build a complex architecture for a tiny problem.

## Mini-mission

- Add an ATTACKING state.
- Prevent movement while attacking.
- Return to the previous active state when the attack finishes.
- Make defeat impossible to undo by ordinary input.
- Test each transition and record how you triggered it.

## Checkpoint

1. What bug can explicit states prevent?
2. Why should defeated state block ordinary movement?
3. When is a simple enum no longer enough?

**Boss challenge:** build an enemy with PATROL, CHASE, ATTACK, and DEFEATED states. Document transition conditions before implementation.

**Common mistakes:** changing state in several unrelated functions, forgetting a transition back, and allowing two state behaviours to run at once.

**Further reading:** [Finite state machines](https://gameprogrammingpatterns.com/state.html) and [Godot nodes](https://docs.godotengine.org/en/stable/classes/class_node.html).
