# 05 — Operators and Expressions

Operators combine or compare values. They let your game calculate scores, check conditions, and update movement or health.

## Arithmetic

```gdscript
var a: int = 10
var b: int = 3

print(a + b) # 13
print(a - b) # 7
print(a * b) # 30
print(a / b) # Numeric division; result depends on operand types
print(a % b) # 1, the remainder
```

Use parentheses when you want to make the order of operations obvious:

```gdscript
var final_score: int = (base_score + bonus) * multiplier
```

Make sure the expression's result is compatible with the variable's type.

## Comparison

Comparison operators produce a Boolean value:

- `==` equal to
- `!=` not equal to
- `>` greater than
- `<` less than
- `>=` greater than or equal to
- `<=` less than or equal to

```gdscript
var health: int = 25
print(health > 0)   # true
print(health == 0)  # false
```

Do not confuse `=` (assignment) with `==` (comparison).

## Logical operators

- `and`: both conditions must be true.
- `or`: at least one condition must be true.
- `not`: reverses a Boolean value.

```gdscript
var has_key: bool = true
var door_unlocked: bool = false

if has_key and not door_unlocked:
    print("The key can unlock the door.")
```

## Updating values

```gdscript
var coins: int = 0
coins += 1
coins -= 1
coins *= 2
```

These compound assignments update the variable using its current value.

## Practice tasks

1. Calculate the remainder of 29 divided by 5.
2. Write a condition that checks whether health is positive.
3. Write a condition that checks whether a player has a key **and** enough coins.
4. Explain the difference between `=` and `==`.
5. Predict the result of `(4 + 2) * 3` before running it.

**Official reference:** [GDScript operators](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
