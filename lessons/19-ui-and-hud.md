# 19 — User Interfaces and HUDs

A HUD (heads-up display) shows useful game information such as health, score, timer, and collected items. Godot's `Control` nodes are designed for UI layouts.

## Common UI nodes

- `Control`: base class for interface elements.
- `Label`: displays text.
- `Button`: responds to presses.
- `ProgressBar`: visualises a value within a range.
- `VBoxContainer` / `HBoxContainer`: arrange children vertically or horizontally.
- `CanvasLayer`: can keep UI visually separate from the world camera.

## Update a Label

Create a `CanvasLayer` with a `Label` child, then attach this script to the CanvasLayer:

```gdscript
extends CanvasLayer

@onready var score_label: Label = $Label

func set_score(score: int) -> void:
    score_label.text = "Score: " + str(score)
```

Call `set_score(new_score)` when the score changes. Converting a number with `str` makes it text that can be combined with the label string.

## Update a health bar

Add a `ProgressBar` named `HealthBar` to the UI scene:

```gdscript
@onready var health_bar: ProgressBar = $HealthBar

func set_health(current: int, maximum: int) -> void:
    health_bar.max_value = maximum
    health_bar.value = current
```

Connect this method to the health component's `health_changed` signal. Signal-driven updates are usually cleaner than checking health every rendered frame when health only changes occasionally.

## Layout tips

Use containers and anchors rather than hard-coded positions for every element. Test the UI at different window sizes. Make text readable, keep important information visible, and consider keyboard/controller navigation and accessibility.

## Practice tasks

1. Display the player's score in a Label.
2. Add a ProgressBar for health.
3. Update both through functions or signals.
4. Resize the game window and adjust anchors or containers so the HUD remains usable.

**Official references:** [User interface](https://docs.godotengine.org/en/stable/tutorials/ui/index.html) · [Control](https://docs.godotengine.org/en/stable/classes/class_control.html)
