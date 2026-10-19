# Advanced GDScript Practice Workbook

This workbook is for learners who have completed the beginner lessons. Try each task before opening the hints. All examples target Godot 4.x. Use a fresh practice project and keep each challenge small enough to debug.

## How to use this workbook

For every challenge:
1. Write down the expected input and output.
2. Build the smallest version that works.
3. Test a normal case and at least two edge cases.
4. Read errors carefully and fix the cause rather than hiding the warning.
5. Explain your solution aloud or in a short note.

## Level 1 — Data and functions

### Challenge 1: Safe healing
Write a function that heals a player by a requested amount. Health must never exceed maximum health, and a negative healing amount must not reduce health.

**Tests:** heal from 40 to 60; heal from 95 with a maximum of 100; attempt to heal with -20.

### Challenge 2: Count inventory
Given an inventory dictionary such as { "apple": 3, "key": 1 }, write a function that returns the number of apples. If the item is missing, return zero.

**Tests:** existing item, missing item, item count of zero.

### Challenge 3: Filter a score list
Given an array of scores, return a new array containing only scores greater than or equal to 100. Do not modify the original array.

**Extension:** sort the new array from highest to lowest.

## Level 2 — Godot architecture

### Challenge 4: Collectible signal
Create an Area2D collectible. When the player enters, emit a signal carrying the collectible's value, then remove the collectible. Ensure it cannot award points twice.

**Think about:** collision layers/masks, checking the body type, and whether the player has a score receiver.

### Challenge 5: Data-driven enemies
Create an EnemyData Resource with display name, max health, speed, and contact damage. Make one enemy scene use the assigned resource. Create two different resources without duplicating the enemy script.

**Tests:** resource assigned, resource missing, two enemies with different values.

### Challenge 6: Explicit enemy states
Implement PATROL, CHASE, ATTACK, and DEFEATED states. Write the transition table first. Make defeated enemies stop moving and stop dealing damage.

**Extension:** add a recovery delay after taking damage.

### Challenge 7: Save migration
Save a dictionary with a format version. Pretend an older save does not contain the coins field. Load it with a sensible default and reject a save whose root is not a dictionary.

**Think about:** a real game should validate field types and ranges, not merely convert arbitrary input.

## Level 3 — Reliability and polish

### Challenge 8: Cooldown without duplicate timers
Create an attack cooldown. Repeated input while the cooldown is active must not create multiple overlapping attacks or timers.

### Challenge 9: Pause-aware timer
Create a countdown and decide explicitly whether it should continue while the game is paused. Test both the intended pause and resume behaviour.

### Challenge 10: Bug report
Give a friend your project and ask them to reproduce a bug without telling them the fix. Record steps, expected result, actual result, and the relevant error message.

### Challenge 11: Refactor a giant function
Take one function that performs several jobs. Split it into small functions with clear names. Do not change the observable behaviour.

### Challenge 12: Missing dependency
Temporarily remove a required Resource or child node. Add a clear warning or error message that tells another developer what needs to be assigned or renamed.

## Boss project — The Tiny Dungeon

Build one short playable level containing:
- A player with movement and health.
- At least two enemy variants configured with Resources.
- A collectible that sends a signal to update score.
- A door that opens only when the player has a key.
- A pause menu and restart flow.
- A save file for one persistent value.
- A clear win condition and a clear lose condition.
- A short README explaining controls, how to run the project, and known limitations.

### Definition of done

- The game can be started and finished without editing the code.
- Missing or invalid data fails safely where practical.
- Every major mechanic has been tested at least once.
- The README tells a new person how to play.
- Third-party assets have been credited according to their licences.

## Hints and example reasoning

- **Challenge 1:** clamp the result between zero and maximum health. Reject negative healing before applying it.
- **Challenge 2:** dictionary get-style access can provide a default for a missing key.
- **Challenge 3:** append qualifying values to a separate result array.
- **Challenge 4:** use a one-time guard or disable monitoring immediately after collection, then emit the signal before removing the node.
- **Challenge 5:** separate design data from runtime state. Health that decreases during play usually belongs to the enemy instance, not shared design data.
- **Challenge 6:** allow only transitions that make sense. Defeated should be terminal unless you intentionally support reviving enemies.
- **Challenge 7:** validate the parsed root and each required field. Defaults are useful, but silently accepting malformed values can hide data problems.
- **Challenge 8:** set the cooldown guard before awaiting the timer.
- **Challenge 9:** choose a timer process mode that matches the desired pause behaviour and verify it in a running project.
- **Challenge 10:** a useful bug report is reproducible by someone who did not write the code.
- **Challenge 11:** refactoring should improve structure without changing the feature's result.
- **Challenge 12:** validate scene dependencies early and include the expected node or resource name in the message.

## Self-assessment

Score each item from 0 to 2:
- 0 = not yet; 1 = partly; 2 = can explain and demonstrate it.

| Skill | Score |
|---|---:|
| I can explain my data types and function return values. | /2 |
| I can use signals to reduce direct dependencies. | /2 |
| I can separate Resource data from instance state. | /2 |
| I can describe and test state transitions. | /2 |
| I can load and validate saved data. | /2 |
| I can use timers without blocking gameplay. | /2 |
| I can reproduce and document a bug. | /2 |
| I can deliver a small game with instructions and credits. | /2 |

A low score is not failure; it tells you what to practise next. Revisit the related lesson, then try the challenge again without looking at the hint.
