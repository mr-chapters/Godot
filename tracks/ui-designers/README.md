# 🖥️ UI Designer Track — Make Menus Clear and Friendly

**Role:** design the parts of a game people click, read, navigate, and use to understand what is happening.

## Level 1 — Know the UI nodes
Start with [UI and HUD](../../lessons/19-ui-and-hud.md).

Common nodes:
- `Control` for UI layout and interaction;
- `Label` for text;
- `Button` for actions;
- `TextureRect` for images;
- `ProgressBar` for values;
- `VBoxContainer` and `HBoxContainer` for automatic layout.

## Level 2 — Build a menu
Create a main menu with Play, Settings, and Quit/Back actions appropriate to your platform. Use anchors and containers so it adapts to different window sizes.

## Level 3 — Give useful feedback
A button should show that it can be pressed and provide feedback when activated. Important messages should be readable and not depend only on sound or colour. Keep controls consistent and allow enough space for touch targets on mobile.

## Mini-mission

Build a pause menu with Resume, Restart, and Settings. Make sure the game pauses and resumes correctly.

## Boss challenge

Create a settings screen with music volume, SFX volume, fullscreen or window-size options where supported, and a clear Back button. Test the menu using a keyboard and a mouse; if targeting mobile, test touch input too.

**Bonus:** save the settings and restore them when the game launches.

**Official reference:** [Godot UI documentation](https://docs.godotengine.org/en/stable/tutorials/ui/index.html)
