# Game Designers & Testers' Book — Chapter 3: Difficulty, Feedback, and Accessibility

> **Mission:** make one challenge easier to understand without removing the challenge itself.

## 1. Difficulty is more than speed

A game can become harder through tighter timing, more enemies, fewer safe spaces, less information, more complex choices, or fewer resources. Increase difficulty deliberately. If every variable gets harder at once, it becomes difficult to tell what the player is learning.

## 2. Teach, then test

A useful early sequence:
1. Show a safe example of a mechanic.
2. Let the player try it with little pressure.
3. Present a variation that tests understanding.
4. Combine it with a previously learned mechanic.
5. Give feedback so the player understands success or failure.

If a player fails, ask whether they understood the mechanic and had enough information to respond. A challenge can be hard and fair; confusion is not the same as difficulty.

## 3. Feedback explains cause and effect

When an action succeeds, the player should receive feedback appropriate to the action: animation, sound, text, controller vibration where supported, or a change in the world. Critical feedback should not depend on one sense alone.

When a player takes damage, consider a brief visual response plus a sound or UI update. Avoid excessive flashing, screen shake, or loud effects that make play uncomfortable.

## 4. Accessibility as design quality

Consider:
- remappable controls where practical,
- subtitles and adjustable text,
- sufficient contrast,
- indicators that do not rely only on colour,
- volume sliders and mute options,
- reducing screen shake or intense visual effects,
- difficulty options or assist features when suitable,
- support for keyboard/controller/touch depending on the target.

Not every project can implement every option, but deciding early prevents expensive redesign later.

## 5. Run a controlled balance test

Change one main variable at a time. For example, test whether widening a platform improves fairness before also changing gravity, movement speed, and checkpoint placement. Record the old value, new value, and result.

Use multiple testers if possible. One person's experience is useful but not universal.

## 6. Mini-mission

Choose one frustrating section. Observe a tester, identify whether the issue is unclear information, execution difficulty, or a bug, then make one targeted adjustment. Test again.

**Boss challenge:** write a short difficulty curve with three levels of the same mechanic: safe introduction, normal test, and advanced combination.

## 7. Checkpoint

1. Why is confusion different from difficulty?
2. Why change one balance variable at a time?
3. Name three accessibility options.
4. Why should critical feedback use more than one channel?

<details><summary>Answer key</summary>

1. Difficulty tests a known challenge; confusion means the player may not understand what is happening or expected.
2. It helps reveal which change caused the effect.
3. Remappable controls, subtitles, contrast, volume controls, reduced shake, and more.
4. Players may miss or not perceive one type of signal.
</details>
