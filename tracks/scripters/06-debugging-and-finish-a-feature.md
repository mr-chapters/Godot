# Scripters' Book — Chapter 6: Debug Like a Developer

> **Mission:** learn a repeatable process for finding bugs instead of changing random lines until the error disappears.

## 1. Errors are clues

When Godot reports an error, read the first relevant message and the file/line it names. The line may be where the problem becomes visible, not where the original mistake happened. Read a few lines above it too.

Common categories:
- **Syntax error:** the code cannot be parsed.
- **Type error:** a value does not match the expected type.
- **Invalid node path:** a node cannot be found at the requested path.
- **Null reference:** a value is missing or has not been initialized.
- **Logic bug:** the code runs but produces the wrong result.

## 2. Make the problem repeatable

Write down:
1. What you did.
2. What you expected.
3. What happened instead.
4. Whether it happens every time.
5. What changed just before it started.

If you cannot reproduce a bug, gather more information before rewriting the feature.

## 3. Print the values you are unsure about

```gdscript
func buy_item(price: int, coins: int) -> bool:
    print("DEBUG price=", price, " coins=", coins)
    if coins >= price:
        print("DEBUG purchase allowed")
        return true
    print("DEBUG not enough coins")
    return false
```

Temporary prints reveal which path the program follows and what values it uses. Remove noisy debug messages or replace them with a deliberate logging strategy before shipping.

## 4. Change one thing at a time

If you change five unrelated lines and the bug disappears, you may not know which change fixed it—or whether another bug was introduced. Make a small change, run the same reproduction steps, and record the result.

## 5. Finish a feature with a checklist

Before calling a feature done:
- Does the normal case work?
- What happens at zero or maximum values?
- What happens if the player repeats the action quickly?
- What happens after restarting the scene?
- Is the output understandable to the player?
- Does the feature still work after another feature changes?

## 6. Mini-mission

Intentionally make a node path incorrect, run the scene, read the error, fix the path, and run it again. Then intentionally make a condition use the wrong comparison and inspect the logic.

Learning to diagnose controlled mistakes is safer than waiting for a big project to fail.

## 7. Boss challenge

Pick one feature—pickup, door, health bar, or pause menu. Write its expected behaviour, test normal and edge cases, fix one issue, and document what changed.

## Checkpoint

1. Why read the first relevant error message?
2. What is a logic bug?
3. Why change one thing at a time?
4. Name three edge cases to test.

<details><summary>Answer key</summary>

1. It often points toward the earliest useful clue.
2. Code runs but does not behave as intended.
3. It helps identify which change caused the result.
4. Zero value, maximum value, repeated input, restart, invalid data, and more.
</details>
