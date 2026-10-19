# 04 — Data Types and Type Hints

## Why types matter

A type describes what kind of value a variable holds. Common GDScript types include:

| Type | Example | Use |
|---|---|---|
| `int` | `42` | Whole numbers |
| `float` | `3.5` | Numbers with fractional parts |
| `String` | `"Hello"` | Text |
| `bool` | `true` | True/false states |
| `Vector2` | `Vector2(1, 0)` | 2D position or direction |
| `Vector3` | `Vector3(0, 1, 0)` | 3D position or direction |
| `Array` | `[1, 2, 3]` | Ordered collection |
| `Dictionary` | `{"coins": 5}` | Key-value data |

## Type inference

Godot can infer a variable's type from its initial value:

```gdscript
var lives = 3
var player_name = "Mira"
var can_jump = true
```

Inference is convenient, but explicitly declaring important types can make code easier to understand.

## Type hints

```gdscript
var lives: int = 3
var move_speed: float = 220.0
var player_name: String = "Mira"
var can_jump: bool = true
```

The colon after the variable name introduces the type hint. A type hint helps the editor catch some mistakes and documents what a value is expected to be.

Functions can also specify argument and return types:

```gdscript
func calculate_total(coins: int, bonus: int) -> int:
    return coins + bonus
```

This function expects integer arguments and returns an integer.

## Null and object references

A variable that stores a reference to a node or object is not the same as a number or text. A reference may be `null`, meaning it does not currently refer to an object. Check references before using them when they might be missing.

```gdscript
var target: Node = null

func _ready() -> void:
    if target == null:
        print("No target has been assigned.")
```

Depending on the exact type and project settings, you may need to use a nullable or inferred type rather than a strict non-null object type. Follow the type system guidance for your Godot version.

## Practice tasks

1. Add type hints to variables for health, speed, player name, and whether a key was collected.
2. Write a typed function that accepts two integers and returns their product.
3. Predict what happens if you try to assign a string to an integer variable. Test it and read the error.
4. Explain why `220` and `220.0` may be treated as different numeric types.

**Official reference:** [GDScript static typing](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/static_typing.html)
