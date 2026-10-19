# Game Designers & Testers' Book — Chapter 2: Find Bugs and Report Them Clearly

> **Mission:** turn “the game is broken” into a report a developer can reproduce and fix.

## 1. What is a bug?

A bug is a behaviour that differs from what the game is intended to do. A player falling through a floor is likely a bug. A player losing health when touching a hazard may be intended. The design brief and expected behaviour help distinguish the two.

## 2. Write a useful bug report

Use this structure:

- **Title:** short and specific.
- **Build/version:** which build did you test?
- **Environment:** operating system, device, resolution, input method if relevant.
- **Steps to reproduce:** exact steps in order.
- **Expected result:** what should happen?
- **Actual result:** what happened instead?
- **Frequency:** every time, sometimes, or once?
- **Evidence:** screenshot, short recording, log, or error message if useful.
- **Severity:** how much does it block play?

Example:

**Title:** Player falls through the floor after restarting Level 1

**Steps:** Start Level 1 → walk to the moving platform → fall → choose Restart.

**Expected:** Player returns to the spawn point and stands on the floor.

**Actual:** Player appears below the floor and keeps falling.

**Frequency:** 3 out of 3 attempts.

This report gives the developer something repeatable to investigate.

## 3. Severity is not the same as annoyance

A typo in an optional menu may be low severity. A crash on launch is high severity. A bug that corrupts saved progress may be severe even if it happens rarely.

Use your team's scale consistently. For example:
- **Blocker:** cannot start or continue the game.
- **High:** major feature broken, progress lost, or common path blocked.
- **Medium:** feature works incorrectly but a workaround exists.
- **Low:** cosmetic or minor inconvenience.

## 4. Regression testing

A regression is a bug that returns or a new problem caused by a change. After fixing a pickup bug, test not only that pickup but also other collectible types and the restart flow.

Keep a small test checklist for critical paths:
- start game,
- move,
- collect item,
- take damage,
- win,
- lose,
- restart,
- save and load if supported.

## 5. Separate evidence from interpretation

Evidence: “The player stopped moving after opening the pause menu.”

Interpretation: “The pause code probably freezes input.”

Both can be useful, but label them separately. The cause might be pause mode, a focus issue, or an input action not being processed.

## 6. Mini-mission

Ask someone to play your prototype for five minutes. Record at least three observations. Turn any unexpected behaviour into a bug report with reproduction steps. Prioritize the issues that block the main loop.

**Boss challenge:** fix one bug, then repeat the original reproduction steps and run a regression test on nearby features.

## 7. Checkpoint

1. Why include exact reproduction steps?
2. What is a regression?
3. Why record the expected and actual result?
4. Is a rare save-corruption bug necessarily low severity?

<details><summary>Answer key</summary>

1. So another person can reproduce and investigate the issue.
2. A problem that returns or is introduced by a change.
3. It makes the mismatch explicit.
4. No; severity depends on impact, not only frequency.
</details>
