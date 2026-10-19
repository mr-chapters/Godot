# 20 — Saving and Loading Data

Saving lets a game remember progress between sessions. You might save settings, a high score, unlocked levels, or the player's current progress.

## Choose what to save

Start with small, serialisable data such as numbers, strings, Booleans, arrays, and dictionaries. Do not assume that every live object or node can be saved directly. Usually you save the important state, then recreate the relevant objects when loading.

## A small JSON save file

```gdscript
extends Node

const SAVE_PATH := "user://savegame.json"

func save_game() -> void:
    var data := {
        "score": 120,
        "level": 2,
        "sound_enabled": true
    }

    var file := FileAccess.open(SAVE_PATH, FileAccess.WRITE)
    if file == null:
        push_error("Could not open save file for writing.")
        return

    file.store_string(JSON.stringify(data))

func load_game() -> Dictionary:
    if not FileAccess.file_exists(SAVE_PATH):
        return {}

    var file := FileAccess.open(SAVE_PATH, FileAccess.READ)
    if file == null:
        push_error("Could not open save file for reading.")
        return {}

    var parsed = JSON.parse_string(file.get_as_text())
    if parsed is Dictionary:
        return parsed

    push_warning("Save data was invalid.")
    return {}
```

The `user://` path points to a writable application data location managed by Godot, rather than the project's source folder. The example returns an empty dictionary if there is no file or its contents are invalid.

## Use the loaded data safely

```gdscript
var save_data: Dictionary = load_game()
var saved_score: int = int(save_data.get("score", 0))
var saved_level: int = int(save_data.get("level", 1))
```

Defaults are important because the save file may be missing keys, created by an older version, or contain unexpected data. For a larger game, add a save-version field and a migration strategy.

## Important security note

A local save file is user-editable. Do not trust it for authoritative online multiplayer results, purchases, or other security-sensitive decisions. This example is for ordinary local game progress, not anti-cheat protection.

## Practice tasks

1. Save a score and load it when the game starts.
2. Add a sound setting to the save dictionary.
3. Test loading when no save file exists.
4. Deliberately corrupt the JSON and make sure your game handles it gracefully.
5. Explain why saving a score is different from saving a live Node object.

**Official reference:** [FileAccess](https://docs.godotengine.org/en/stable/classes/class_fileaccess.html) · [JSON](https://docs.godotengine.org/en/stable/classes/class_json.html)
