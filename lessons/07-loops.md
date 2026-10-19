# 07 — Loops

A loop repeats code. Use loops to process enemies, add up scores, inspect items, or repeat an action a known number of times.

## for loop with a range

```gdscript
for number in range(5):
    print(number)
```

This prints 0, 1, 2, 3, and 4. The end value passed to `range` is excluded.

```gdscript
for number in range(1, 6):
    print(number)
```

This prints 1 through 5.

## Loop through an array

```gdscript
var items: Array[String] = ["Potion", "Key", "Map"]

for item in items:
    print(item)
```

The variable `item` takes each value from the array, one at a time.

## while loop

A `while` loop repeats as long as its condition remains true.

```gdscript
var countdown: int = 3

while countdown > 0:
    print(countdown)
    countdown -= 1

print("Go!")
```

**Important:** the condition must eventually become false. If you never update `countdown`, the loop can run forever and freeze the game or editor.

## break and continue

- `break` exits the current loop early.
- `continue` skips the rest of the current iteration and moves to the next one.

Use them when they make the intention clearer, not to hide complicated control flow.

## Game example: total collected coins

```gdscript
var collected: Array[int] = [2, 5, 1]
var total: int = 0

for amount in collected:
    total += amount

print(total) # 8
```

## Practice tasks

1. Print numbers from 1 to 20.
2. Print only even numbers from 2 to 20.
3. Find the total of `[10, 15, 4]`.
4. Write a countdown that prints "Go!" at the end.
5. Explain why a `while` loop that never changes its condition can be dangerous.

**Official reference:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
