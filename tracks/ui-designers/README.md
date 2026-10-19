# 🖥️ UI Designers' Book — Make Menus Clear and Friendly

**Who this book is for:** interface designers and developers building menus, HUDs, settings, and player feedback. Good UI helps players understand the game instead of fighting it.

## Table of contents

1. [Build Your First HUD](01-your-first-game-hud.md) — Control nodes, CanvasLayer, score, health bars, layout, and readability.
2. [Menus, Layout, and Accessibility](02-menus-layout-and-accessibility.md) — containers, pause menus, process mode, and accessible interaction.
3. [Settings, Feedback, and Preferences](03-settings-feedback-and-save-options.md) — volume controls, immediate feedback, ConfigFile preferences, and defaults.
4. [Navigation, Input, and UI Testing](04-navigation-input-and-ui-testing.md) — menu flow, keyboard/controller support, responsive layouts, and testing.

## UI design rules
- Every control should have a clear purpose.
- Use containers and anchors for adaptable layouts.
- Keep text readable and buttons clearly labelled.
- Do not rely on colour or sound alone for critical feedback.
- Make focus visible for keyboard/controller navigation.
- Test at different window sizes.
- Ensure buttons do what their labels promise.
- Save settings only when you can restore them reliably.

## Further learning
- [Official Godot UI documentation](https://docs.godotengine.org/en/stable/tutorials/ui/index.html)
- [Godot Control class reference](https://docs.godotengine.org/en/stable/classes/class_control.html)
- [Main GDScript course](../../README.md)

**Graduation challenge:** build a main menu, gameplay HUD, pause menu, and settings screen. Make them navigable with a mouse and keyboard, and verify that volume settings persist after restarting the game.
