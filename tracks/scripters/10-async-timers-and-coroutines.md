# Chapter 10 — Timers, Await, and Time-Based Logic

**Mission:** make cooldowns, temporary effects, dialogue pauses, and delayed actions without freezing the game.

## Do not pause the whole game to wait

A common beginner mistake is creating a delay with a long loop. That blocks the main thread and can make the game appear frozen. In Godot, use a Timer node or await a signal for time-based behaviour.

## Await a timer signal

~~~gdscript
extends Node

func _ready() -> void:
    print("Round starts")
    await get_tree().create_timer(2.0).timeout
    print("Two seconds have passed")
~~~

The function pauses at await until the timer's timeout signal arrives, then continues. The game can keep processing other work while the function waits.

## Cooldown example

~~~gdscript
extends Node

@export var cooldown_seconds: float = 0.8
var can_attack: bool = true

func try_attack() -> void:
    if not can_attack:
        return

    can_attack = false
    perform_attack()
    await get_tree().create_timer(cooldown_seconds).timeout
    can_attack = true

func perform_attack() -> void:
    print("Attack!")
~~~

Call try_attack() from your input logic. The guard prevents repeated calls from starting multiple cooldowns. If pause behaviour matters, configure the timer's process mode intentionally.

## Timer node or create_timer?

Use a Timer node when the timer is visible in the scene and needs Inspector configuration, repeated timeouts, or editor-driven connections. Use get_tree().create_timer() for a small one-off delay.

## Be careful with overlapping async calls

Think through what happens if the node is removed while awaiting, if the scene changes, or if the game pauses. Async logic should have a clear owner and expected lifetime.

## Mini-mission

1. Add a temporary speed boost lasting three seconds.
2. Prevent the player from stacking ten boosts accidentally.
3. Make a countdown that updates a label once per second.
4. Test pause and scene-change behaviour.

## Checkpoint

- What does await wait for?
- Why is a blocking delay a bad idea in a game loop?
- How do you prevent duplicate cooldowns?

**Boss challenge:** make a wave countdown, spawn a group of enemies, then wait until the wave is cleared before starting the next countdown.

**Further reading:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html) and [Timer](https://docs.godotengine.org/en/stable/classes/class_timer.html).
