# Scripters' Book — Chapter 3: Decisions, Loops, and Functions

> **Mission:** build the rules for a tiny arcade game: collect coins, lose health when hit, and unlock the exit when the score is high enough.

## Decisions: let the game choose

An `if` statement runs instructions only when a condition is true.

```gdscript
var health: int = 40

func check_health() -> void:
    if health <= 0:
        print("Game over!")
    elif health < 30:
        print("Careful! Low health.")
    else:
        print("You can keep going.")
```

Godot checks the conditions from top to bottom. The first true branch runs. Indentation defines which lines belong to each branch. Use `elif` for another condition and `else` for the fallback.

Combine conditions with `and`, `or`, and `not`. For example, `if has_key and score >= 10:` requires both conditions to be true.

## Loops: repeat work without copy-paste

```gdscript
for coin_number in range(3):
    print("Coin ", coin_number)
```

`range(3)` produces 0, 1, and 2. The loop runs three times. Use a `for` loop when you know what collection or range to process.

```gdscript
var countdown: int = 3

while countdown > 0:
    print(countdown)
    countdown -= 1
print("Go!")
```

A `while` loop continues while its condition is true. Make sure something changes the condition; otherwise the loop may never finish and can freeze the game.

## Functions: give one job a name

Functions make code easier to read, reuse, and test.

```gdscript
func can_open_exit(has_key: bool, coins: int) -> bool:
    return has_key and coins >= 5

func _ready() -> void:
    if can_open_exit(true, 7):
        print("Exit unlocked!")
    else:
        print("Find a key and five coins.")
```

The values in parentheses are parameters. The type after `->` describes the returned value. `return` sends the answer back to the caller and ends that function.

## Practice lab: arcade rules

Write a script that:
1. Starts with 3 lives and 0 coins.
2. Prints a message for each coin from 1 to 5.
3. Adds one coin each time through the loop.
4. Uses an `if` statement to print “Exit unlocked” when coins reach 5.
5. Uses a function that returns whether the player has any lives left.

## Debugging habits

- Print the values used by a condition when the wrong branch runs.
- Test boundary values: 0, 1, the exact target, and one below the target.
- If a loop freezes the editor, inspect whether its condition ever becomes false.
- Keep functions focused. A function called `update_score` should not also save settings, spawn enemies, and open menus.

## Boss challenge

Create a mini text-based quest with a key, coins, and health. Use at least one function, one loop, and one decision. Add comments explaining why the exit does or does not open.

## Checkpoint

1. What does `elif` do?
2. What does `return` do?
3. Why can a `while` loop freeze a game?
4. What values does `range(3)` produce?

<details><summary>Answer key</summary>

1. Tests another condition if previous conditions were false.
2. Sends a value back to the caller and ends the function.
3. Its condition may remain true forever.
4. 0, 1, 2.
</details>
