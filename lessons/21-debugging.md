# 21 — Debugging and Reading Errors

Debugging is the process of finding and fixing the cause of unexpected behaviour. It is a normal part of programming; experienced developers debug too.

## Read the first useful error

When Godot reports an error:
1. Read the message and identify the script and line number.
2. Open that script and inspect the named line and nearby code.
3. Check spelling, indentation, types, node paths, and whether a referenced object exists.
4. Form a specific hypothesis about the cause.
5. Change one thing, run again, and see whether the result supports your hypothesis.

Fix the earliest meaningful error first. Later errors may be consequences of the first one.

## Print useful state

```gdscript
func take_damage(amount: int) -> void:
    print("Damage requested: ", amount)
    print("Health before damage: ", current_health)
    current_health -= amount
    print("Health after damage: ", current_health)
```

Temporary prints can show which code ran and what values it used. Remove or reduce noisy debug prints once the issue is resolved.

## Use the debugger

Godot's debugger can pause execution, show the call stack, inspect variables, and step through code. A breakpoint pauses on a line so you can examine the state at that moment. This is often more useful than adding dozens of print statements.

## Common error categories

- **Parser/syntax error:** the code cannot be parsed; check punctuation, indentation, and names.
- **Invalid access:** a value or reference is not what the code expects.
- **Node not found:** a path or node name does not match the scene tree.
- **Type error:** a value is incompatible with the expected type.
- **Logic bug:** code runs without an error, but the result is wrong. Reproduce it and inspect assumptions.

## Practice tasks

1. Create a typo, observe the error, and fix it.
2. Set a breakpoint inside a function and inspect its arguments.
3. Reproduce a bug with the smallest possible example.
4. Write down the expected result before each test.

**Official reference:** [Debugger and troubleshooting](https://docs.godotengine.org/en/stable/tutorials/scripting/debug/index.html)
