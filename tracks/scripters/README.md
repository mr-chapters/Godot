# 🧠 Scripter Track — Teach Your Game to Think

**Role:** write the rules and behaviour that make a game playable.

You are the person who makes the character move, doors open, coins count, enemies react, menus work, and progress save. You do not need to know everything on day one. Build one small behaviour at a time.

## Level 1 — Learn the language
1. [GDScript foundations](../../lessons/02-first-script.md)
2. [Variables and constants](../../lessons/03-variables-and-constants.md)
3. [Types and type hints](../../lessons/04-types-and-type-hints.md)
4. [Operators](../../lessons/05-operators.md)
5. [Conditions](../../lessons/06-conditions.md)
6. [Loops](../../lessons/07-loops.md)
7. [Functions](../../lessons/08-functions.md)
8. [Arrays and dictionaries](../../lessons/09-arrays-and-dictionaries.md)

**Mini-mission:** create a score counter that increases when you collect a coin.

## Level 2 — Think in Godot
1. [Nodes and scenes](../../lessons/12-nodes-scenes-tree.md)
2. [Node lifecycle](../../lessons/13-node-lifecycle.md)
3. [Input and movement](../../lessons/14-input-and-movement.md)
4. [Signals](../../lessons/15-signals.md)
5. [Collision and Area2D](../../lessons/16-collision-and-area2d.md)

**Mini-mission:** make a player collect an item and notify the score system using a signal.

## Level 3 — Build real systems
1. [Timers and spawning](../../lessons/17-timers-and-spawning.md)
2. [Health and game states](../../lessons/18-health-and-game-states.md)
3. [UI and HUD](../../lessons/19-ui-and-hud.md)
4. [Saving and loading](../../lessons/20-saving-and-loading.md)
5. [Debugging](../../lessons/21-debugging.md)
6. [Clean code](../../lessons/22-clean-code.md)

**Mini-mission:** build a small game with health, a timer, a game-over state, and a restart button.

## Scripter habits that save hours

- Read the error message before changing random lines.
- Check node names and paths carefully.
- Give variables and functions names that explain their purpose.
- Use signals when one system needs to announce an event to another.
- Test one feature at a time.
- Learn why code works, not only what to paste.

## Boss challenge

Create a reusable door with a locked state. It should open when the player has a key, play a sound, and emit a signal when opened. Add a message when the player has no key.

**Bonus:** make the door save its open state and explain how you would test that save data.
