# 22 — Clean Code and Project Organisation

Working code is not automatically easy-to-maintain code. Clear names, small functions, predictable structure, and consistent conventions help you understand your own project later and make collaboration easier.

## Use descriptive names

Prefer `enemy_health`, `move_speed`, and `calculate_total_score` over vague names like `x`, `thing`, or `do_stuff`. Names should describe purpose, not merely type.

## Keep functions focused

A function that reads input, moves a character, saves data, updates the UI, and spawns enemies has too many responsibilities. Split unrelated tasks into smaller functions or systems.

Small functions are easier to test and reuse, but don't split every single line into a new function. Choose boundaries that make the intent clearer.

## Avoid repeated logic

If several places calculate damage differently, bugs and balancing problems become likely. Put shared rules in a reusable component or function and have callers use it.

## Organise files by responsibility

A small project might look like:

```text
res://
├── scenes/
│   ├── player/
│   ├── enemies/
│   ├── levels/
│   └── ui/
├── scripts/
│   ├── systems/
│   └── utilities/
├── art/
├── audio/
└── project.godot
```

This is an example, not a rule. For small projects, keeping a script next to its scene can be convenient. Choose a layout that makes files easy to find and use it consistently.

## Comments should explain why

A comment that repeats the code adds little value. Explain surprising design decisions, important constraints, or why a non-obvious approach is necessary. Update comments when behaviour changes.

## Practice tasks

1. Rename vague variables in one of your scripts.
2. Split a long function into smaller responsibilities.
3. Find duplicated logic and decide whether it should be shared.
4. Organise a small project into clear folders.
5. Review your code as if another beginner will need to understand it.

**Official reference:** [GDScript style guide](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_styleguide.html)
