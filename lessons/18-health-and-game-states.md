# 18 — Health, Damage, and Game States

Health is a simple example of a system that multiple parts of a game may need to use. Keep the rules for health in one place so every enemy, hazard, and UI element does not invent its own version.

## A small health component

```gdscript
extends Node
class_name HealthComponent

signal health_changed(current: int, maximum: int)
signal died

@export var max_health: int = 100
var current_health: int

func _ready() -> void:
    current_health = max_health
    health_changed.emit(current_health, max_health)

func take_damage(amount: int) -> void:
    if amount <= 0 or current_health <= 0:
        return

    current_health = maxi(current_health - amount, 0)
    health_changed.emit(current_health, max_health)

    if current_health == 0:
        died.emit()

func heal(amount: int) -> void:
    if amount <= 0 or current_health <= 0:
        return

    current_health = mini(current_health + amount, max_health)
    health_changed.emit(current_health, max_health)
```

Attach the script to a node in your character scene, then call its `take_damage(10)` method when a hazard or enemy hit should reduce health. Because it emits signals, a HUD can update without being tightly coupled to the health component.

## Why clamp values?

Health should not drop below zero or rise above the maximum. `maxi` and `mini` keep the value inside those boundaries. The script also ignores non-positive damage and healing to avoid surprising results.

For a production game, decide how healing works after death, whether damage can be blocked, and whether repeated death events are possible. The right rules depend on your game.

## Game states

As projects grow, use explicit states to describe major modes such as `MENU`, `PLAYING`, `PAUSED`, and `GAME_OVER`. Enums help avoid magic numbers:

```gdscript
enum GameState { MENU, PLAYING, PAUSED, GAME_OVER }
var state: GameState = GameState.MENU
```

A state should have clear transitions. For example, a game-over state might stop enemy spawning and ignore movement input. Avoid spreading contradictory state checks throughout many unrelated scripts.

## Practice tasks

1. Add a healing function and ensure health never exceeds maximum health.
2. Connect the `health_changed` signal to a Label.
3. Connect `died` to a game-over handler.
4. Write down valid state transitions for a simple game: menu → playing → paused → playing, or playing → game over.

**Official references:** [Signals](https://docs.godotengine.org/en/stable/getting_started/step_by_step/signals.html) · [GDScript enums](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
