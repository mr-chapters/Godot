# Pixel Artists' Book — Chapter 1: Pixel Art and Readable Sprites

> **Mission:** create a small character sprite that remains recognisable at game size.

## Pixel art is controlled simplification
Pixel art is not simply art with a small brush. Each pixel is a deliberate choice. With a limited resolution, silhouette, contrast, and colour grouping often matter more than tiny details.

A good sprite should still be recognisable:
- at its intended size,
- against the actual game background,
- while moving,
- when seen quickly.

## Start with the silhouette
Draw the character as one solid shape. Can someone recognise it from the outline alone? If the head, body, and feet merge into one blob, simplify the outline or separate important shapes.

Then add:
1. a base colour,
2. a shadow colour,
3. a highlight,
4. one or two identity details.

A limited palette is a helpful constraint for beginners, not a universal rule.

## Pick a canvas and tool
Try a 16×16 or 32×32 canvas for practice. The right resolution depends on the game style and camera.

Tools:
- [LibreSprite](https://libresprite.github.io/)
- [Piskel](https://www.piskelapp.com/)
- [Aseprite](https://www.aseprite.org/) (paid; check current terms)
- [Kenney assets](https://kenney.nl/assets) for prototyping

Export transparent PNG when you need transparency, and keep editable source files so you can revise the art later.

## Light and shadow
Choose a light direction and keep it consistent. If the light comes from the upper left, highlights generally belong on upper-left-facing surfaces and shadows on lower-right-facing surfaces. Avoid adding random highlight pixels just to make the sprite busier.

## Bring it into Godot
1. Put the PNG in `art/sprites/`.
2. Create a Sprite2D.
3. Assign the PNG to its Texture property.
4. If the image looks blurry, inspect texture filtering. Pixel art often benefits from nearest-neighbour filtering.
5. Test at the intended viewport size.

Fractional scaling can make pixel widths look uneven. Choose your base resolution and scaling approach deliberately.

## Mini-mission
Create normal, damaged, and powered-up versions of the same character. Keep the silhouette consistent but change a few colours or details to communicate the state.

**Boss challenge:** place the sprite against three backgrounds and make sure it remains readable on all of them.

## Checkpoint
1. Why begin with a silhouette?
2. Why keep the editable source file?
3. What can fractional scaling do to pixels?
4. Why keep light direction consistent?

<details><summary>Answer key</summary>

1. It tests recognition before details distract.
2. It allows future edits without recreating the sprite.
3. It can make pixel widths uneven or blurry.
4. It makes objects feel visually coherent.
</details>

**Next:** [Spritesheets, animation, and export](02-spritesheets-animation-and-export.md).
