# Builders' Book — Chapter 5: Routes, Checkpoints, and Level Flow

> **Mission:** design a short level that teaches one mechanic, rewards exploration, and gives players a fair restart point.

## 1. Build the route before the decoration

Sketch the level as a sequence of spaces. Each space should have a purpose: teach, challenge, rest, reward, or transition. A corridor that has no decision, surprise, or pacing purpose may be unnecessary.

A reliable beginner structure:
1. **Safe start:** learn controls.
2. **First test:** use one mechanic with little risk.
3. **Combination:** use the same mechanic with another obstacle.
4. **Optional reward:** reward curiosity.
5. **Checkpoint:** reduce repeated frustration.
6. **Final test:** combine learned skills.
7. **Exit:** clearly show completion.

## 2. Guide attention without forcing one route

Players follow visual contrast, landmarks, light, motion, and object placement. Use these cues to suggest a route, but let players explore when exploration is part of the design.

Try this test: hide the instructions and watch a new player. If everyone misses the exit, improve the layout before adding a long explanation.

## 3. Checkpoints and recovery

A checkpoint should be easy to identify and should save the progress that players reasonably expect it to save. Decide whether it resets enemies, collectibles, doors, or puzzles. A checkpoint that returns the player to a confusing or unsafe position creates more frustration than it removes.

For a simple 2D game, the checkpoint may store a spawn position or a named checkpoint ID. Keep the rule consistent and test it after death and after restarting the scene.

## 4. Optional routes and rewards

A good optional route communicates risk and reward. The player should be able to judge whether the reward is worth the detour. Use a visible collectible, unusual landmark, or a slightly harder path to signal the opportunity.

Avoid making optional rewards look mandatory unless the game actually requires them.

## 5. Level review checklist

- Can the player identify the start and goal?
- Does each area teach or test something?
- Are hazards readable before they cause damage?
- Is the route fair for the movement system?
- Are checkpoints placed before frustrating repeated sections?
- Can the player tell optional rewards from required objectives?
- Does the camera show enough of the upcoming challenge?

## 6. Boss challenge

Build a level with two routes: a safe, longer route and a risky, shorter route with an optional reward. Have two testers play it and compare which route they choose and why. Use observations rather than assuming what they will prefer.

## Checkpoint

1. Why give each area a purpose?
2. What should a checkpoint rule specify?
3. How can players discover an optional route?
4. Why test a level with instructions hidden?

<details><summary>Answer key</summary>

1. It improves pacing and removes unnecessary empty space.
2. Where the player returns and which parts of progress persist or reset.
3. Landmarks, visual cues, and a visible reward.
4. To find out whether the environment communicates its own goals.
</details>
