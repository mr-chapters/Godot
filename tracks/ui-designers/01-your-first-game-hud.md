# UI Designers' Book — Chapter 1: Build Your First HUD

> **Mission:** make a player status display with a title, score, and health bar. Your HUD should help the player without covering the action.

## 1. What is a HUD?

A heads-up display (HUD) shows useful information while the game is being played: health, score, timer, objective, ammunition, or collected items. A menu helps the player choose actions; a HUD helps the player understand the current game state.

Ask three questions before adding an element:
1. What question does this element answer?
2. How quickly does the player need the answer?
3. Can the player still see the game?

If an element does not help the player make a decision or understand the game, consider removing it.

## 2. Use Control nodes for interface

Godot has a separate family of UI nodes called **Control** nodes. Common ones include:
- `Label`: display text.
- `Button`: clickable action.
- `ProgressBar`: show a numeric value as a bar.
- `TextureRect`: show an image inside a UI layout.
- `PanelContainer`: panel background and child layout.
- `VBoxContainer` / `HBoxContainer`: arrange children vertically or horizontally.
- `MarginContainer`: add space around content.
- `CenterContainer`: centre a child in the available area.

Use containers where possible rather than manually positioning every child. Containers can resize and rearrange their children when the window changes.

## 3. Build the scene

Create a new scene with a root `CanvasLayer` named `HUD`. Add a `Control` child named `Layout`, then add:
- a Label named `ScoreLabel`;
- a ProgressBar named `HealthBar`;
- a Label named `HealthLabel`.

Anchor Layout to the full available screen using the Layout menu in the editor. Position the score near the upper-left and health near the upper-right, leaving room for the game action. Set the ProgressBar's minimum and maximum values to 0 and 100.

A CanvasLayer keeps the HUD visually separate from the moving 2D world camera. This is useful for screen-space interface elements.

## 4. Update the HUD with a script

Attach this script to HUD. The child paths must match your scene tree exactly.

```gdscript
extends CanvasLayer

@onready var score_label: Label = $Layout/ScoreLabel
@onready var health_bar: ProgressBar = $Layout/HealthBar
@onready var health_label: Label = $Layout/HealthLabel

func set_score(value: int) -> void:
    score_label.text = "Score: %d" % value

func set_health(value: int, maximum: int = 100) -> void:
    health_bar.max_value = maximum
    health_bar.value = clampi(value, 0, maximum)
    health_label.text = "Health: %d / %d" % [value, maximum]

func _ready() -> void:
    set_score(0)
    set_health(100)
```

### Understand the important lines

- `@onready` stores references to child controls after the node is ready.
- `$Layout/ScoreLabel` is a node path. If you rename or move that node, update the path.
- `set_score()` is a reusable method that receives a score value.
- `set_health()` sets the bar's maximum and current values.
- `clampi(value, 0, maximum)` keeps the displayed bar value within the valid range.
- `"%d" % value` formats an integer into a string. The text assigned to a Label must be a String.

This HUD has methods that other scripts can call. For a larger project, signals are often a good way for a health or score system to announce changes without needing to know the exact HUD node.

## 5. Make it readable

- Use enough contrast between text and background.
- Keep labels short and consistent.
- Do not communicate low health with colour alone; add a number, icon, animation, or other cue.
- Keep the HUD away from important action.
- Test at the smallest window size you support.
- Check whether longer text or translated labels still fit.

## 6. Mini-mission

Add a coin counter and an objective label. Write an example objective such as “Find 3 batteries.” Make the objective update when the player makes progress.

**Boss challenge:** create a low-health state that changes the HUD's presentation, but still communicates health clearly to someone who cannot distinguish the chosen colours.

## 7. Common bugs

- **Invalid get index or null reference:** check node names and paths.
- **Bar never changes:** confirm that `set_health()` is called with the new value.
- **HUD moves with the camera:** put screen-space UI under a CanvasLayer.
- **Text is cut off:** use containers, anchors, and minimum-size settings, then test smaller windows.
- **Health bar exceeds its range:** set the maximum and clamp the value.

## 8. Checkpoint

1. What is the difference between a HUD and a main menu?
2. Why use a CanvasLayer for a screen-space HUD?
3. What does a ProgressBar's max_value mean?
4. Why should low health not be communicated by colour alone?

<details><summary>Answer key</summary>

1. A HUD shows live gameplay information; a menu offers navigation or choices.
2. It keeps the HUD separate from world-camera movement.
3. The upper bound of its represented value.
4. Colour may not be visible to every player and is not always noticed quickly.
</details>
