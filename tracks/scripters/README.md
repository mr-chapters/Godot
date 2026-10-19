# 🧠 Scripters' Book — Teach Your Game to Think

**Who this book is for:** beginners who want to write the rules behind movement, inventory, enemies, UI, quests, and saving. Read the chapters in order and type examples yourself. The core course in `lessons/` adds more depth and practice.

## Table of contents

### Part I — Start thinking like a programmer
1. [Your First Script](01-your-first-script.md) — create a scene, attach GDScript, run it, and understand `_ready()`.
2. [Variables, Stats, and Types](02-variables-stats-and-types.md) — strings, integers, floats, booleans, constants, scope, and calculations.
3. [Decisions, Loops, and Functions](03-decisions-loops-and-functions.md) — conditions, repetition, parameters, and return values.
4. [Input, Movement, and Signals](04-input-movement-and-signals.md) — Input Map actions, CharacterBody2D movement, and node communication.
5. [Arrays, Dictionaries, and Inventory](05-arrays-dictionaries-and-inventory.md) — collections, item counts, and inventory rules.
6. [Debugging and Finishing a Feature](06-debugging-and-finish-a-feature.md) — read errors, reproduce bugs, test edge cases, and finish responsibly.

### Part II — Connect the foundations to Godot
Continue with the main [GDScript lesson course](../../README.md):
- [Nodes, scenes, and the scene tree](../../lessons/12-nodes-scenes-tree.md)
- [The node lifecycle](../../lessons/13-node-lifecycle.md)
- [Input and movement](../../lessons/14-input-and-movement.md)
- [Signals](../../lessons/15-signals.md)
- [Collision and Area2D](../../lessons/16-collision-and-area2d.md)
- [Timers and spawning](../../lessons/17-timers-and-spawning.md)
- [Health and game states](../../lessons/18-health-and-game-states.md)
- [UI and HUD](../../lessons/19-ui-and-hud.md)
- [Saving and loading](../../lessons/20-saving-and-loading.md)
- [Clean code](../../lessons/22-clean-code.md)

### Part III — Final project
Build a small game with movement, collectibles, health, an exit condition, and a restart flow. Then extend it with a door that requires a key and a score requirement.

## How to study this book
For each chapter: read the mission, build the setup, type the example, run it, change one value, complete the mini-mission, and answer the checkpoint without looking at the answer. If an example fails, compare node names, input action names, indentation, and the first error message.

## Scripter's field rules
- Keep each function focused on one job.
- Prefer clear names over clever names.
- Use signals when systems need to communicate without tightly depending on each other.
- Test normal cases and edge cases.
- Do not paste code you cannot explain.
- Read the official [GDScript reference](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/index.html).

**Graduation challenge:** create a small, playable game and explain how movement, health, score, signals, and win/lose states connect.
