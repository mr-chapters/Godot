# Scripters' Book — Chapter 2: Give Your Game a Memory

> **Mission:** store a player name, health, score, and key status, then change those values during a mission.

## Variables are labelled storage
A variable is a named place for a value. A health variable remembers how much health remains; a score variable remembers points.

```gdscript
var player_name: String = "Nova"
var health: int = 100
var score: int = 0
var has_key: bool = false
```

- `var` creates a variable.
- `String` is text.
- `int` is a whole number.
- `float` is a number that can have a decimal.
- `bool` is either `true` or `false`.
- `=` assigns the starting value.

Type hints such as `: int` make the intended data clearer and help Godot detect mistakes.

## Print and change values

```gdscript
extends Node2D

var player_name: String = "Nova"
var health: int = 100
var score: int = 0

func _ready() -> void:
    print("PLAYER: ", player_name)
    print("HEALTH: ", health)
    score += 10
    health -= 25
    print("After mission — health: ", health, " score: ", score)
```

`score += 10` means add 10 to the current score. `health -= 25` subtracts 25 from health. The final values are 75 health and 10 score.

## Constants are rules that should not change

```gdscript
const MAX_HEALTH: int = 100
var health: int = MAX_HEALTH
```

A constant is useful for a fixed rule such as maximum health. If several systems need the same fixed value, a constant avoids repeated unexplained numbers.

## Comparisons and calculations

```gdscript
var coins: int = 7
var coin_value: int = 5
var money: int = coins * coin_value
var can_buy: bool = money >= 30
```

Math operators include `+`, `-`, `*`, `/`, and `%`. Comparison operators include `==`, `!=`, `>`, `<`, `>=`, and `<=`.

Remember: `=` assigns a value, while `==` asks whether two values are equal.

## Where does a variable exist?
A variable declared at the top level of a script can be used by its methods. A variable created inside a function is normally local to that function.

```gdscript
var score: int = 0

func add_point() -> void:
    var bonus: int = 1
    score += bonus
```

Here, `score` is available to the script's methods. `bonus` belongs to `add_point()`.

## Mini-mission
Create variables for a player name, health, gems, and whether a chest is open. Print them, add three gems, then open the chest and print the updated values.

**Boss challenge:** make a constant called `GEMS_TO_WIN` and a function that returns whether the player has collected enough gems.

## Common mistakes
- Storing text in an integer variable: use a suitable type or convert deliberately.
- Using `=` where you meant `==`: assignment and comparison are different.
- Using a local variable outside its function: move it to an appropriate scope if multiple methods need it.
- Using unclear names: prefer `player_health` over `x`.

## Checkpoint
1. Which type represents `false`?
2. What is the difference between `=` and `==`?
3. What is health after starting at 100 and subtracting 25?
4. Why use a constant for maximum health?

<details><summary>Answer key</summary>

1. `bool`.
2. Assignment versus comparison.
3. 75.
4. It keeps a fixed rule consistent and easier to change.
</details>

**Next:** [Decisions, loops, and functions](03-decisions-loops-and-functions.md).
