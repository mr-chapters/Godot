# 🎨 Pixel Artist Track — Create Crisp Game Art

**Role:** create sprites, tiles, backgrounds, and animations that communicate clearly at small sizes.

## Level 1 — Make a readable sprite
Try [Piskel](https://www.piskelapp.com/) or [LibreSprite](https://libresprite.github.io/).

Learn:
- choose a small canvas and use a limited palette;
- make the silhouette recognisable before adding details;
- use consistent light direction;
- check that important features remain visible at actual game size;
- export as PNG and keep editable source files where possible.

## Level 2 — Create animation
Make idle, run, jump, and hurt animations. Keep frame sizes consistent and use timing that communicates weight. Not every animation needs many frames; clear timing often matters more than detail.

## Level 3 — Import into Godot
Read the [pixel-art manual](../../manual/pixel-art/README.md).

- Use nearest filtering when you want crisp pixels.
- Check texture import and project scaling settings.
- Test the game at its intended resolution.
- Avoid accidental fractional scaling that makes pixel widths uneven.
- Keep animation names consistent.

## Mini-mission

Create a character, one enemy, a floor tile, a wall tile, and a collectible. Import them into Godot and make sure each remains readable at normal gameplay size.

## Boss challenge

Create a 16×16 or 32×32 character with idle and walk animations, then build a small tileset around the same palette.

**Bonus:** create a second palette for a different mood without changing the silhouette.
