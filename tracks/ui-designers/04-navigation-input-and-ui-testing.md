# UI Designers' Book — Chapter 4: Navigation, Input, and UI Testing

> **Mission:** make a menu that can be used with a mouse and keyboard, and that survives a smaller game window.

## 1. Menus are a flow, not a pile of screens

Map the user's journey before building:
- Main Menu → Play → Gameplay
- Main Menu → Settings → Back
- Gameplay → Pause → Resume
- Pause → Main Menu, with confirmation if progress may be lost

Every screen needs a clear next step and a clear way back. Avoid dead ends where a player has to close the game to escape.

## 2. Mouse, keyboard, controller, and touch

Choose input methods based on the game and platform. If supporting keyboard navigation, make sure focus can move between buttons and that the focused control is visible. Test Enter/Space activation where appropriate. For touch, make targets large enough and leave space between them.

Do not assume a mouse click proves the UI is complete.

## 3. Test different sizes

Use containers and anchors, then test:
- normal window size,
- smaller window size,
- wide aspect ratio,
- narrow aspect ratio if supported,
- longer text,
- large text if the project allows it.

If a button disappears off-screen, fix the layout rather than telling players to resize the window.

## 4. Test state changes

A button should do what its label promises. Resume should unpause. Back should return to the previous screen. A volume slider should change the correct bus. Restore Defaults should restore actual values and saved preferences.

Use a small checklist and test each path after making changes.

## 5. Mini-mission

Ask someone to use your menu without instructions. Give them tasks such as “turn down music,” “return to the main menu,” and “resume the game.” Note where they hesitate.

## 6. Boss challenge

Create a menu-flow diagram and implement each path. Test it with mouse and keyboard. Add a confirmation step before an action that can discard unsaved progress.

## Checkpoint

1. Why should every screen have a clear way forward or back?
2. Why is mouse-only testing incomplete?
3. What should happen when a button's label says Resume?
4. Why test longer text and smaller windows?

<details><summary>Answer key</summary>

1. Users need to navigate without becoming trapped.
2. Players may use keyboard, controller, or touch.
3. The game should resume and the pause menu should close.
4. Layout problems often appear only under those conditions.
</details>
