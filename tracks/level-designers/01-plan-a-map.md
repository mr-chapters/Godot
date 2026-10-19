# Chapter 1 — Plan a Map Before Building

**Mission:** design a level with a clear goal, meaningful choices, and a route that suits the game's movement.

## 1. Start with the game loop

Ask what the player does most often. A platformer needs space to jump, land, and read hazards. A top-down adventure needs clear routes, enemy spacing, and room to dodge. A puzzle game needs readable information and places to experiment.

Do not start by drawing random rooms. Start with the actions the player should perform and the feeling you want the level to create.

## 2. Write a tiny level brief

- **Goal:** what counts as finishing?
- **Core action:** what does the player repeatedly do?
- **Challenge:** what skill does this level teach or test?
- **Landmark:** what helps the player understand where they are?
- **Reward:** what makes exploration worthwhile?
- **Exit:** how does the player know they succeeded?

Keep the first map small enough to finish and test quickly.

## 3. Draw the route first

Use boxes and arrows before art. For example:

~~~text
START → Safe tutorial area → First challenge → Reward room
                                  ↓
                              Optional path
                                  ↓
                              Main exit
~~~

A route diagram is a promise about the player's experience, not a final map. It shows the order of spaces and decisions; it does not dictate every wall.

## 4. Use pacing

A simple pattern is **learn → practise → combine → breathe → test**. Introduce one mechanic in a safe place, let the player practise it, combine it with something familiar, then provide a quieter moment before a harder challenge.

## 5. Mini-mission

Sketch a small level on paper or in a drawing app. Mark the start, goal, one obstacle, one optional reward, and one landmark. Label what the player learns in each area.

## Checkpoint

- What should you decide before placing decorations?
- How does a landmark help?
- Why might an optional path be useful?

**Boss challenge:** design two different routes to the same goal: one short and risky, one longer and safer. Write down the trade-off each route offers.

**Diagram — the level-design loop**

~~~mermaid
flowchart TD
    A[Define player goal] --> B[Sketch route]
    B --> C[Build greybox]
    C --> D[Playtest]
    D --> E{Can players navigate and enjoy it?}
    E -- No --> B
    E -- Yes --> F[Add art and sound]
    F --> G[Test again]
~~~

**Further reading:** [Godot documentation](https://docs.godotengine.org/en/stable/) and [Game Programming Patterns](https://gameprogrammingpatterns.com/).
