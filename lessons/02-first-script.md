# 02 — Your First GDScript

## Attach a script

Open your `Main.tscn` scene and select its root node. Click **Attach Script**, keep the default GDScript language, and create the script. Godot opens a new `.gd` file.

Replace the contents with:

```gdscript
extends Node

func _ready() -> void:
    print("Hello, game developer!")
```

Run the current scene and look at the Output panel. You should see the message.

## Understand every line

- `extends Node` means this script inherits the built-in `Node` class. It gets the behaviour and properties available to a Node.
- `func` begins a function definition.
- `_ready()` is a lifecycle callback Godot calls when the node and its children have entered the scene tree and are ready.
- `-> void` says the function does not return a value.
- `print(...)` writes a message to the Output panel.
- The indented line belongs to the function. GDScript uses indentation to show code blocks.

The function name is `_ready`, with an underscore. Spelling and capitalisation matter.

## Change the example

Try this:

```gdscript
extends Node

func _ready() -> void:
    print("Starting my game")
    print(2 + 3)
    print("I can change this message.")
```

The output should contain three lines. The expression `2 + 3` is calculated before `print` displays it.

## Common mistakes

- Writing `Func` instead of `func`.
- Forgetting the colon after the function signature.
- Indenting the function body incorrectly.
- Typing the code in a script that is not attached to the scene you run.
- Looking at the game viewport instead of the Output panel.

## Practice tasks

1. Print your own welcome message.
2. Print the result of `12 * 4`.
3. Add a second function named `show_level_name` and call it from `_ready`.
4. Deliberately misspell `print`, run the project, and read the error. Fix it afterward.

**Official references:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html) · [Node class](https://docs.godotengine.org/en/stable/classes/class_node.html)
