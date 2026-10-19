# UI Designers' Book — Chapter 3: Settings, Feedback, and Preferences

> **Mission:** design a settings screen that remembers the player's preferences and gives clear feedback when they change something.

## 1. Settings are part of the experience

Useful settings can include:
- master volume,
- music volume,
- sound-effects volume,
- window mode or resolution where supported,
- screen shake,
- subtitles or text size where supported,
- control remapping.

Do not add settings only because another game has them. Each setting needs a clear effect and should work reliably.

## 2. Use a slider with a clear value

A slider should show what it controls and ideally expose the current value. For a volume slider, map a normalised value from 0.0 to 1.0 to decibels using Godot's audio helpers or the bus API. Audio volume is logarithmic, so a linear percentage does not correspond directly to a linear perceived loudness change.

A conceptual update method:

```gdscript
func set_music_volume(value: float) -> void:
    var safe_value := clampf(value, 0.0, 1.0)
    # Route the Music bus in the Audio panel before using this.
    var bus_index := AudioServer.get_bus_index("Music")
    if bus_index >= 0:
        AudioServer.set_bus_volume_db(
            bus_index,
            linear_to_db(maxf(safe_value, 0.001))
        )
```

This uses a tiny floor to avoid converting exact zero into negative infinity; for a fully muted state, you can mute the bus separately when the slider reaches zero. The bus named Music must exist.

## 3. Give immediate feedback

When the player moves a slider, the sound should change immediately so they can judge the setting. When a button is pressed, make the state change visible. When an action fails, explain why in plain language.

Avoid feedback that depends only on a sound; players may have muted the game. Avoid feedback that flashes too quickly to read.

## 4. Save preferences

Godot can store small user preferences in a configuration file under the user data directory. A simple ConfigFile pattern:

```gdscript
extends Node

const SETTINGS_PATH := "user://settings.cfg"

func save_volume(value: float) -> void:
    var config := ConfigFile.new()
    var error := config.load(SETTINGS_PATH)
    # A missing file is normal on first launch.
    config.set_value("audio", "music_volume", clampf(value, 0.0, 1.0))
    var save_error := config.save(SETTINGS_PATH)
    if save_error != OK:
        push_warning("Could not save settings: %s" % save_error)

func load_volume() -> float:
    var config := ConfigFile.new()
    var error := config.load(SETTINGS_PATH)
    if error != OK:
        return 0.8
    return clampf(float(config.get_value("audio", "music_volume", 0.8)), 0.0, 1.0)
```

The first load may fail because the file does not exist yet; returning a default is expected. In a production settings manager, handle load and save errors clearly and consider saving all settings together rather than repeatedly recreating the file for every control change.

## 5. Lab

Build a settings menu with music and SFX sliders. Add labels showing the current percentage. Change the actual buses, save the values, restart the game, and confirm the settings load again.

## 6. Accessibility review

- Can the player understand each setting without guessing?
- Is keyboard focus visible?
- Are sliders usable with a controller if you support one?
- Is the current value displayed?
- Can the player restore defaults?
- Does the UI still work with longer translated text?

## 7. Boss challenge

Add a “Restore Defaults” button with a confirmation step. Make sure it resets the controls and the saved values—not just the labels on screen.

## Checkpoint

1. Why is immediate audio feedback useful?
2. Why return a default when a settings file is missing?
3. Why should zero volume be handled intentionally?
4. What should Restore Defaults actually change?

<details><summary>Answer key</summary>

1. It lets players judge the setting as they change it.
2. A first-time launch has no saved preferences yet.
3. The decibel conversion of zero is not a finite number.
4. The actual settings, displayed controls, and saved preferences.
</details>
