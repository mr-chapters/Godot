# Project 01 — Top-Down Collector

Build a small 2D game in which the player moves around a room and collects items. This project combines input, scenes, collisions, signals, and UI.

## Goal

Create a playable level with a controllable player, at least five collectibles, a score counter, and a win message when every collectible has been collected.

## Requirements

- A `CharacterBody2D` player with a sprite and collision shape.
- Four Input Map actions for movement.
- A collectible scene built around `Area2D`.
- A score value that increases exactly once per collected item.
- A HUD Label that shows the current score.
- A message or state that indicates the level is complete.

## Suggested build order

1. Create the main scene and player scene.
2. Implement and test player movement in an empty room.
3. Create one collectible and test its collision.
4. Emit a signal when the collectible is picked up.
5. Make a level controller track the score.
6. Update the HUD when the score changes.
7. Add several collectible instances to the level.
8. Detect when the required number has been collected.
9. Test the entire loop from starting the game to winning.

## Design constraints

Keep responsibilities separated:
- The player handles movement.
- The collectible detects pickup and removes itself.
- The level or game controller tracks progress.
- The HUD displays progress.

You may choose a different structure if you can explain why it is useful.

## Stretch challenges

- Add a timer and show the remaining time.
- Add an enemy that follows the player.
- Add a sound effect for collecting an item.
- Save the best score.
- Add a restart button.

## Completion checklist

- [ ] The player moves in all four directions.
- [ ] Collision works reliably.
- [ ] Collectibles disappear only once.
- [ ] Score updates correctly.
- [ ] The win condition triggers at the right time.
- [ ] There are no unresolved errors in the debugger.
- [ ] Another person can play without you explaining the controls.

## Reflection

Write down the hardest bug you encountered, how you reproduced it, and what finally fixed it. This is part of learning software development, not extra paperwork.
