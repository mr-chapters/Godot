# Chapter 2 — Blockouts, Scale, and Navigation

**Mission:** make the level playable with simple shapes before adding final art.

## 1. What is a blockout?

A blockout (also called a greybox) is a rough version of the level made from cubes, rectangles, platforms, and placeholder doors. It answers gameplay questions: can the player jump that gap, see the next platform, fit through the doorway, and understand where to go?

A beautiful level can still fail if its geometry is confusing. Test the shape and flow first.

## 2. Use a consistent scale

Choose a reference size such as the player's height, then use it to judge doors, stairs, platforms, corridors, and cover. In 2D, keep tile dimensions and collision sizes consistent. In 3D, choose a grid unit and snap modular pieces to it when appropriate.

Scale is a starting point, not a law: playtesting decides whether the space feels right.

## 3. Guide without forcing

Use a combination of:
- **Silhouette:** the destination has a recognisable shape.
- **Contrast:** important paths differ visually from background areas.
- **Landmarks:** a tower, bright doorway, unusual tree, or coloured banner.
- **Framing:** walls or props naturally point toward the next area.
- **Safe sightlines:** players can see enough to make a decision.

Do not rely on colour alone to communicate critical information. Combine colour with shape, symbols, lighting, or placement.

## 4. Test movement, not screenshots

Run through the level at the actual player speed. Test the maximum jump, fall distance, camera view, collision edges, and the route while moving. A screenshot cannot tell you whether a jump is fair.

## Mini-mission

Build three rooms from simple shapes: a safe room, a movement challenge, and a reward room. Test them without decorative props.

## Checkpoint

1. What gameplay questions does a blockout answer?
2. Why use a reference size?
3. Name three ways to guide players without arrows.

**Boss challenge:** ask a friend to play the blockout. Watch where they hesitate or get stuck. Change the level, not just your explanation.

**Diagram — sightline and route concept**

~~~text
[START] ── visible path ──> [LANDMARK]
   │                            │
   └── optional side route ──> [REWARD]
                                │
                             [GOAL]
~~~

**Further reading:** [Godot 2D](https://docs.godotengine.org/en/stable/tutorials/2d/index.html) and [Godot 3D](https://docs.godotengine.org/en/stable/tutorials/3d/index.html).
