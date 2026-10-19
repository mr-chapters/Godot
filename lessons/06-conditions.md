# 06 — Conditions: if, elif, and else

Conditions let your game choose what to do. A door may open if the player has a key; an enemy may flee when its health is low.

## Basic if statement

```gdscript
var health: int = 40

if health > 0:
    print("The player is alive.")
```

The indented body runs only when the condition evaluates to `true`.

## Add else

```gdscript
if health > 0:
    print("Keep playing.")
else:
    print("Game over.")
```

Exactly one of these branches runs: the first when health is positive, the second otherwise.

## Several possibilities with elif

```gdscript
var score: int = 720

if score >= 1000:
    print("Gold rank")
elif score >= 500:
    print("Silver rank")
elif score >= 100:
    print("Bronze rank")
else:
    print("Keep practising")
```

Godot tests the conditions from top to bottom and runs the first matching branch. Order matters: put more restrictive or higher thresholds first when needed.

## Combining conditions

```gdscript
var has_key: bool = true
var door_is_open: bool = false

if has_key and not door_is_open:
    print("Open the door.")
elif door_is_open:
    print("Walk through.")
else:
    print("Find the key.")
```

Keep conditions readable. If a line becomes difficult to understand, give part of the logic a descriptive variable name.

## Common mistakes

- Forgetting the colon after the condition.
- Incorrect indentation.
- Using `=` instead of `==` when comparing.
- Putting a broad condition before a more specific condition so the later branch never runs.
- Writing a complicated condition without testing its different cases.

## Practice tasks

1. Print "Low health" when health is below 25.
2. Give the player a rank based on score using at least three thresholds.
3. Check whether a player has both a key and enough coins to unlock a chest.
4. Test your logic with values below, exactly at, and above each threshold.

**Official reference:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
