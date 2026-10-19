# UI Designers' Book — Chapter 2: Menus, Layout, and Accessibility

> **Mission:** create a pause menu that can be understood, navigated, and dismissed.

## Design the information before the decoration

Write down the menu's purpose before styling it. A pause menu usually needs a clear title, Resume, Settings, and Main Menu or Quit depending on the game. Keep the most common action easy to find.

Use a hierarchy:
- Heading: what screen is this?
- Primary action: what should the player do most often?
- Secondary actions: settings and navigation.
- Supporting text: control hints or warnings.

Do not make every button equally bright and large. Contrast should help players find the next action.

## Control nodes and containers

Godot UI is built with Control nodes. Containers such as VBoxContainer and HBoxContainer arrange their children automatically. Anchors and offsets help position controls relative to their parent.

A simple scene tree:

```text
PauseMenu (Control)
└── CenterContainer
    └── PanelContainer
        └── VBoxContainer
            ├── Label
            ├── ResumeButton
            ├── SettingsButton
            └── MainMenuButton
```

Use containers for groups of controls instead of placing every button at arbitrary coordinates. This makes layouts more adaptable to different window sizes.

## Build a basic pause menu

Create the nodes above and rename the buttons. Set each button's Text in the Inspector. Attach a script to PauseMenu:

```gdscript
extends Control

func _ready() -> void:
    hide()

func open_menu() -> void:
    show()
    get_tree().paused = true

func close_menu() -> void:
    get_tree().paused = false
    hide()
```

This is the menu's visibility logic, not a complete pause system. Connect ResumeButton's `pressed` signal to `close_menu()`. Set the PauseMenu node's **Process > Mode** to **When Paused** (wording can vary slightly by Godot version), otherwise the menu may not receive input while the rest of the tree is paused.

A game controller or level script can call `open_menu()`. Make sure you have a reliable way to reopen or close the menu, such as an input action checked by a node that still processes while paused.

## Accessibility basics

- Use readable text sizes and strong text/background contrast.
- Do not communicate status by colour alone.
- Ensure buttons have clear labels, not just vague icons.
- Make keyboard/controller focus visible and testable.
- Keep important controls in a predictable order.
- Test at smaller window sizes and with longer text.
- Avoid rapid flashing and unnecessary motion.

## Lab

Create a pause menu with Resume, Settings, and Main Menu. Connect each button to a clearly named method. For the Main Menu action, use your project's actual main-menu scene path rather than guessing a path.

## Common bugs

- **Buttons are cut off:** use containers and test a smaller viewport.
- **Pause menu cannot be clicked:** check mouse filtering, visibility, z-order, and pause process mode.
- **Game remains paused after closing:** unpause before hiding or changing scenes.
- **Text is hard to read:** improve contrast and spacing instead of adding more decoration.

## Boss challenge

Make the menu usable with both mouse and keyboard. Test whether a player can understand each option without being told what it does.

## Checkpoint

1. Why use VBoxContainer?
2. Why must a pause menu process while the game is paused?
3. Name three accessibility improvements.
4. Why avoid relying on colour alone?

<details><summary>Answer key</summary>

1. It arranges children vertically and adapts spacing/layout.
2. Otherwise its controls may stop receiving events while the tree is paused.
3. Readable text, contrast, clear labels, keyboard focus, predictable order, and more.
4. Players may not distinguish the colours, and colour alone gives weak information.
</details>
