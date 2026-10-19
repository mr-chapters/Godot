# Game Designers & Testers' Book — Chapter 4: Scope, Milestones, and Release Testing

> **Mission:** turn a game idea into a small finished build instead of an endless list of features.

## 1. Scope is a design skill

A feature costs time to implement, test, explain, and maintain. For a first project, choose one core mechanic and a small set of supporting systems. Extra ideas belong on a future list until the core loop works.

Use three lists:
- **Must have:** without it, the game cannot deliver its main experience.
- **Should have:** improves the experience but can be postponed.
- **Could have:** optional polish or stretch goals.

If the project is late, protect the must-haves and cut optional scope rather than removing testing time.

## 2. Work in milestones

Example milestones:
1. **Prototype:** movement and the main action work.
2. **Playable:** start, goal, success/failure, restart.
3. **Content complete:** intended levels and assets are present.
4. **Polish:** sound, UI, effects, and tuning.
5. **Release candidate:** testing, credits, export, and final fixes.

A milestone should have a clear test that proves it is complete.

## 3. Keep a known-issues list

Before release, record issues that remain. Prioritize by impact and likelihood. Do not hide a serious issue because the release date is close. Decide whether it blocks release or can be clearly documented.

## 4. Release checklist

- [ ] Main scene launches on a clean start.
- [ ] Player can complete the core loop.
- [ ] Win, failure, pause, and restart work.
- [ ] Controls and UI are understandable.
- [ ] Sound levels are comfortable and adjustable where needed.
- [ ] Save/load works if included.
- [ ] No obvious debug labels or test-only controls remain.
- [ ] Third-party assets have the required credits/licences.
- [ ] Export is tested on the target platform.
- [ ] README explains controls and how to play.
- [ ] Known issues are documented honestly.

## 5. Mini-mission

Take an existing prototype and classify every planned feature as Must, Should, or Could. Choose a release milestone and write the test that proves it is complete.

## 6. Boss challenge

Prepare a small release candidate, ask another person to test it from a fresh launch, and create a final report with fixed issues, known issues, and a list of improvements for the next version.

## Checkpoint

1. Why is scope control part of design?
2. What makes a milestone measurable?
3. Why document known issues?
4. Why test an exported build instead of only running inside the editor?

<details><summary>Answer key</summary>

1. It protects the core experience and leaves time to finish and test.
2. It has a clear condition or test for completion.
3. Users and developers need to know about remaining limitations.
4. Export settings and platform behaviour can differ from the editor.
</details>
