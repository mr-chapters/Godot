# 15 — Signals and Communication

Signals let one object announce that something happened without needing to know every object that reacts to it. For example, a collectible can emit a signal when collected, while the level listens and updates the score.

## Why signals are useful

Without signals, one object may need direct references to several other objects. This creates tight coupling: changing one system can force changes elsewhere. Signals allow a sender and a receiver to communicate through an event.

## Diagram — signal communication

The sender announces an event. Receivers react without the sender needing to control how each receiver works.

~~~mermaid
flowchart LR
    A[Collectible] -->|collected signal| B[Level manager]
    B --> C[Update score]
    B --> D[Update HUD]
~~~

## Create a signal

```gdscript
extends Node
signal score_changed(new_score: int)

var score: int = 0

func add_score(points: int) -> void:
    score += points
    score_changed.emit(score)
```

The line `signal score_changed(new_score: int)` declares the signal. When the score changes, `.emit(score)` sends the event and its argument.

## Connect a signal in code

```gdscript
extends Node

@onready var score_source: Node = $ScoreSource

func _ready() -> void:
    score_source.score_changed.connect(_on_score_changed)

func _on_score_changed(new_score: int) -> void:
    print("Score is now: ", new_score)
```

This assumes a child named `ScoreSource` has the first script attached. The callback name is your choice, but it must accept compatible arguments.

You can also connect many built-in signals using the Node dock's **Signals** tab in the editor. Editor connections are often convenient for scene-specific events.

## Built-in signal example

An `Area2D` has a `body_entered` signal. A collectible can react when a body enters its area. Make sure the Area2D has a collision shape and that collision layers and masks allow detection.

## Common mistakes

- Connecting to the wrong node path.
- Declaring a signal but never emitting it.
- Emitting a signal with arguments that do not match what the receiver expects.
- Forgetting to enable the relevant collision monitoring for physics signals.

## Practice tasks

1. Add a typed `health_changed` signal to a health component.
2. Connect it to another node and print the new health.
3. Emit a `collected` signal from a collectible.
4. Explain why the collectible should not need to know how the HUD draws the score.

**Official reference:** [Using signals](https://docs.godotengine.org/en/stable/getting_started/step_by_step/signals.html)
