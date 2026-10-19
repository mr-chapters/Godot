# Chapter 6 — Playtesting, Optimization, and Final Handoff

**Mission:** prove that the level works for someone who did not build it.

## 1. Test with a question

Do not just ask, “Is it fun?” Ask a testable question:
- Can players find the exit without hints?
- Do players notice the optional reward?
- Is the jump consistently possible?
- Can enemies reach the player without getting stuck?
- Does the map remain readable during combat?

Observe before explaining. The moment you give directions, you stop measuring whether the map communicates by itself.

## 2. Write useful notes

Record:
- What the tester tried to do.
- Where they hesitated or failed.
- What they expected to happen.
- What actually happened.
- A screenshot or short reproduction path if useful.

Change one major thing at a time and test again.

## 3. Performance basics

Large numbers of unique materials, expensive real-time shadows, excessive geometry, and too many active objects can affect performance. Measure before optimising. Use Godot's profiler and test on hardware similar to your target audience.

## 4. Final handoff checklist

- [ ] Start and goal are clear.
- [ ] All intended paths are traversable.
- [ ] Collisions and navigation have been tested.
- [ ] Collectibles, hazards, and exits work.
- [ ] Performance has been checked on target hardware where possible.
- [ ] Required assets are credited and licence terms followed.
- [ ] The project README explains controls and how to run the level.
- [ ] Known bugs or unfinished areas are documented.

## Mini-mission

Give your map to someone else and ask them to reach the goal without instructions. Use their behaviour to identify one navigation problem and one gameplay problem. Fix and retest both.

## Checkpoint

1. Why observe without helping?
2. Why profile before optimising?
3. What should a handoff tell the next developer?

**Boss challenge:** publish a playable map project with screenshots, controls, a short design note, credits, and known limitations.

**Diagram — testing loop**

~~~mermaid
flowchart LR
    A[Set a test question] --> B[Observe a player]
    B --> C[Record evidence]
    C --> D[Change the map]
    D --> E[Retest]
    E --> B
~~~
