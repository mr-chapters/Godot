# Scripters' Book — Chapter 1: Your First Script

> **Mission:** create a scene, attach a GDScript file, run it, and make Godot print a message.

## What does a scripter do?
A scripter writes the rules that make the game react. Art shows a door; code decides when it opens. Sound provides a pickup effect; code decides when to play it. You can learn one small behaviour at a time.

Godot projects are built from **nodes** arranged into **scenes**. A **script** adds custom behaviour to a node. The **Output** panel shows printed messages and other useful information.

## Create a tiny project
1. Open Godot 4 and create a project named `ScriptLab`.
2. Create a **2D Scene** and rename the root node `Game`.
3. Save it as `game.tscn`.
4. Select Game and choose **Attach Script**. Keep GDScript as the language.
5. Replace the generated script with the example below.
6. Save and press **F6** to run the current scene.

```gdscript
extends Node2D

func _ready() -> void:
    print("Welcome to ScriptLab!")
    print("The game has started.")
```

## Read every line
- `extends Node2D`: this script inherits the features of a Node2D node.
- `func`: declares a function, a named group of instructions.
- `_ready()`: Godot calls this lifecycle callback when the node and its children are ready in the scene tree.
- `-> void`: declares that the function does not return a value.
- `print()`: writes information to the Output panel.
- Indentation shows which lines belong to the function. Keep it consistent.

Expected output:

```text
Welcome to ScriptLab!
The game has started.
```

## Your own function
Defining a function does not automatically run it. Call it:

```gdscript
extends Node2D

func _ready() -> void:
    show_quest()

func show_quest() -> void:
    print("Quest accepted: find the missing sandwich.")
```

Godot enters `_ready()`, then your code calls `show_quest()`.

## Common mistakes
- **Nothing prints:** check that you ran the current scene with F6 and attached the script to Game.
- **Red parser error:** inspect quotes, brackets, spelling, and indentation on the indicated line.
- **Function not found:** make the call and function definition use the exact same spelling.
- **Wrong scene opens:** set the main scene in Project Settings or run the current scene.

## Mini-mission
Change the messages so they introduce your own game idea. Add a third message describing the first objective.

**Boss challenge:** create two functions, `show_title()` and `show_objective()`, and call both from `_ready()`.

## Checkpoint
1. What is a script for?
2. Where does `print()` show text?
3. Does defining a custom function automatically run it?
4. Who calls `_ready()`?

<details><summary>Answer key</summary>

1. It adds custom behaviour to a node.
2. The Output panel.
3. No; it must be called or connected to an event/callback.
4. Godot calls it during the node lifecycle when the node becomes ready.
</details>

**Next:** [Variables, stats, and types](02-variables-stats-and-types.md).
