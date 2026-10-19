# 08 — Functions and Return Values

A function is a named block of code that performs a task. Functions help you avoid repeating logic and give your program a clear structure.

## Define and call a function

```gdscript
extends Node

func greet_player() -> void:
    print("Welcome back!")

func _ready() -> void:
    greet_player()
    greet_player()
```

Defining a function does not automatically run it. It runs when something calls it.

## Parameters

Parameters let a function work with different inputs:

```gdscript
func greet(name: String) -> void:
    print("Welcome, " + name + "!")

func _ready() -> void:
    greet("Ari")
    greet("Sam")
```

Here, `name` is a parameter. The strings passed when calling the function are arguments.

## Return a result

A function can return a value to the code that called it:

```gdscript
func calculate_damage(base_damage: int, bonus: int) -> int:
    return base_damage + bonus

func _ready() -> void:
    var damage: int = calculate_damage(10, 3)
    print(damage) # 13
```

The return type `-> int` tells the reader and editor that the function returns an integer. `return` sends the result back and ends that function call.

## Separate calculation from action

A calculation function is often easier to test if it calculates a result without changing unrelated game state.

```gdscript
func clamp_health(value: int, maximum: int) -> int:
    return clampi(value, 0, maximum)
```

This function returns a value between zero and the supplied maximum. The caller decides whether and where to store it.

## Good function names

Use verbs or clear descriptions: `take_damage`, `calculate_score`, `open_door`, `is_enemy_nearby`. A function should generally have one understandable responsibility.

## Practice tasks

1. Write a function that prints a level's name.
2. Write `multiply(a: int, b: int) -> int`.
3. Write a function that returns true when a number is positive.
4. Refactor repeated score logic into a single function.
5. Explain the difference between a parameter, an argument, and a return value.

**Official reference:** [GDScript functions](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
