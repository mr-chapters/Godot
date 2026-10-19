# 03 — Variables and Constants

## What is a variable?

A variable is a named place to store a value. A game may store the player's health, current score, movement speed, or name.

```gdscript
extends Node

var player_name = "Nova"
var score = 0
var health = 100

func _ready() -> void:
    print(player_name)
    print(score)
    score = score + 10
    print(score)
```

The output includes `Nova`, then `0`, then `10`. The assignment `score = score + 10` calculates the old score plus ten and stores the result back into `score`.

## Declaration and assignment

- `var score = 0` declares a variable and gives it an initial value.
- `score = 20` changes the value later.
- `score += 5` is shorthand for adding five to the existing value.
- A name should describe the value's purpose. Prefer `enemy_health` over `x` when storing enemy health.

## Constants

A constant is a name for a value that should not be reassigned.

```gdscript
const MAX_HEALTH: int = 100
const GAME_TITLE: String = "Sky Explorer"

var health: int = MAX_HEALTH
```

Use constants for fixed settings such as a maximum health value or a stable game title. Don't use a constant for something that must change during play, such as the player's current health.

## Scope: where a name can be used

A variable declared directly in a script is generally a member of that script instance and can be accessed by its methods. A variable declared inside a function is local to that function.

```gdscript
extends Node

var score: int = 0

func add_point() -> void:
    var points_to_add: int = 1
    score += points_to_add
```

Here, `score` is available to the script's methods. `points_to_add` exists only inside `add_point`.

## Common mistakes

- Using a variable before assigning a useful value.
- Accidentally reusing a name for a different purpose.
- Trying to assign a new value to a constant.
- Expecting a local variable to be accessible from another function.
- Using unclear names that make the code hard to understand.

## Practice tasks

1. Create variables for a player's name, score, and health.
2. Increase the score twice and print the final value.
3. Create a `MAX_HEALTH` constant and use it to initialise health.
4. Write a function that adds a given number of points to the score.

**Official reference:** [GDScript basics — variables and constants](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
