# Pixel Artists' Book — Chapter 3: Tilesets, Backgrounds, and Art Direction

> **Mission:** create a small environment kit that looks like one world and stays readable during gameplay.

## 1. Build a visual rulebook

Before drawing many assets, choose a few rules:
- base tile size,
- palette or colour families,
- light direction,
- outline style,
- level of detail,
- shape language,
- how interactive objects differ from decoration.

These are your art direction. They make a set of separately drawn objects feel like they belong together.

## 2. Design a small tileset

Start with the pieces that your first room actually needs:
- ground centre,
- outer edge,
- inner corner,
- wall,
- floor-to-wall corner,
- one decorative tile,
- one hazard or special tile.

Check that edges connect cleanly. A tile that looks good alone may create visible seams when repeated. Test the tiles in a grid early rather than waiting until the whole tileset is finished.

## 3. Backgrounds need depth, not noise

Use layers to suggest distance:
- far background: broad, low-detail shapes;
- middle layer: landmarks and large silhouettes;
- gameplay layer: high-contrast player, platforms, and hazards;
- foreground: only details that do not hide important action.

A background can be attractive while staying quiet. If it competes with the player, reduce contrast or detail in the background rather than adding outlines to everything.

## 4. Export and organise assets

Use descriptive paths such as `art/characters/hero_idle.png`, `art/tiles/forest_tiles.png`, and `art/backgrounds/cave_far.png`. Keep source files and exported PNGs. Document tile size and animation frame dimensions in a small art README.

## 5. Mini-mission

Create a 5–8 tile environment kit and use it to build one complete room. Add one landmark so players can tell which area they are in.

**Boss challenge:** make the same room feel safe and dangerous using palette changes while keeping the walkable route, player, and hazards easy to distinguish.

## 6. Checkpoint

1. Why define art direction before drawing many assets?
2. Why test tiles in a grid?
3. What is the job of a far-background layer?
4. Why can too much contrast in the background hurt gameplay?

<details><summary>Answer key</summary>

1. It keeps assets visually consistent and reduces rework.
2. It reveals seams and edge problems.
3. To establish distance and atmosphere without competing with gameplay.
4. It can distract from the player and important interactive objects.
</details>
