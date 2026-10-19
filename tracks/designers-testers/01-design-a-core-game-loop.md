# Game Designers & Testers' Book — Chapter 1: Design a Game Loop That Feels Good

> **Mission:** design a one-minute game that teaches one mechanic, challenges it, and rewards the player.

## 1. What is a core loop?

A core loop is the repeating cycle of actions the player performs. In a simple collector game:

1. Explore the room.
2. Spot a collectible.
3. Move toward it.
4. Collect it and receive feedback.
5. Use the reward to unlock a goal.
6. Repeat with a slightly new challenge.

If the action has no interesting decision, the loop may feel empty. If the reward is unclear, players may not understand why they should repeat it.

## 2. Write the design in one sentence

Use this template:

**The player [action] to [goal], while [challenge] makes it interesting.**

Example: “The player collects glowing batteries to power an exit, while moving platforms make the route risky.”

Keep the first version small enough to finish. A polished one-room game teaches more than an enormous design that never becomes playable.

## 3. Make a tiny design brief

Write down:
- **Player fantasy:** what should the player feel like?
- **Core action:** what do they do most?
- **Goal:** how do they know they have succeeded?
- **Failure or pressure:** what creates tension?
- **Feedback:** what sound, animation, or message confirms an action?
- **Session length:** how long should one attempt take?
- **Audience:** who is the game for?

A brief is a decision tool, not a promise that everything must stay fixed. Change it when testing reveals a better idea.

## 4. Prototype the loop with placeholders

Do not begin by drawing the final art. Use shapes and simple sounds. The first prototype should answer one question: “Is the central action fun enough to repeat?”

A useful prototype needs:
- a start,
- one controllable action,
- one challenge,
- clear feedback,
- a goal or end state,
- a way to restart or play again.

## 5. Playtest without leading the player

Give a tester the build and ask them to think aloud. Avoid saying “go over there” or “press this now,” because that hides confusing design. Observe:
- where they look,
- what they try,
- where they hesitate,
- what they misunderstand,
- whether they notice the feedback,
- whether they want another attempt.

Record observations separately from guesses about why they happened.

## 6. Measure useful things

You do not need a large analytics system. Track a few questions:
- Did the tester understand the goal?
- Did they finish the level?
- Where did they fail or get stuck?
- Did they notice the pickup or warning?
- Did they want to replay?

A single tester is not proof that every player will behave the same way, but it can reveal major usability problems.

## 7. Mini-mission

Design a one-room game using the one-sentence template. Prototype it with placeholders and let someone try it without your explanation. Make one change based on what you observe.

**Boss challenge:** remove one feature you like but that does not support the core loop. Explain why the smaller game is clearer.

## 8. Checkpoint

1. What is a core loop?
2. Why prototype with placeholders?
3. Why should you avoid telling a tester what to do?
4. What is the difference between an observation and a guess?

<details><summary>Answer key</summary>

1. The repeating sequence of actions and feedback that defines play.
2. To test gameplay before investing heavily in art and polish.
3. It prevents you from seeing whether the game explains itself.
4. An observation records what happened; a guess proposes why it happened.
</details>
