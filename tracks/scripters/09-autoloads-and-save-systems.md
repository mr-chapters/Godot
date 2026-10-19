# Chapter 9 — Autoloads, Global Services, and Save Data

**Mission:** keep score, settings, and progress available between scenes without turning every script into one giant global script.

## What is an Autoload?

An Autoload is a script or scene registered under Project > Project Settings > Globals > Autoload. Godot creates it as a globally accessible node. It can be useful for a session manager, audio settings, or save service.

Create game_session.gd:

~~~gdscript
extends Node

var score: int = 0
var coins: int = 0

func add_score(amount: int) -> void:
    if amount <= 0:
        return
    score += amount
~~~

Register it as GameSession. Other scripts can call GameSession.add_score(10).

## Use globals carefully

Good uses include data that genuinely spans scenes. Avoid putting every function and every node reference into one Autoload. A global dependency can make tests harder and hide which system owns a value.

## Save a small dictionary

Create save_service.gd and register it as SaveService:

~~~gdscript
extends Node

const SAVE_PATH := "user://savegame.json"

func save_game() -> bool:
    var data := {
        "version": 1,
        "score": GameSession.score,
        "coins": GameSession.coins
    }

    var file := FileAccess.open(SAVE_PATH, FileAccess.WRITE)
    if file == null:
        push_error("Could not open save file for writing.")
        return false

    file.store_string(JSON.stringify(data))
    return true

func load_game() -> bool:
    if not FileAccess.file_exists(SAVE_PATH):
        return false

    var file := FileAccess.open(SAVE_PATH, FileAccess.READ)
    if file == null:
        push_error("Could not open save file for reading.")
        return false

    var parsed: Variant = JSON.parse_string(file.get_as_text())
    if typeof(parsed) != TYPE_DICTIONARY:
        push_warning("Save file is invalid or has an unsupported format.")
        return false

    var data: Dictionary = parsed
    GameSession.score = int(data.get("score", 0))
    GameSession.coins = int(data.get("coins", 0))
    return true
~~~

This is a teaching example, not a complete production save system. It checks the parsed root and supplies defaults for missing keys, but a real game should validate every field, handle version migrations, and decide what to do with corrupted files.

## Save design checklist

- Save only data the player expects to persist.
- Use user://, not a hard-coded desktop path.
- Include a save format version.
- Validate values when loading; a save file is input, not guaranteed truth.
- Decide when to save and how to communicate failure.
- Test first launch, missing file, malformed file, and older save versions.

## Mini-mission

Add a saved best_score that never decreases. Show a message when saving fails. Then add a reset-save button with a confirmation step.

## Checkpoint

- What is an Autoload good for?
- Why should save data be validated?
- Why include a format version?

**Boss challenge:** save the player's settings and unlocked level. Change scenes, restart the game, load the save, and verify the settings and progress return.

**Further reading:** [Autoloads](https://docs.godotengine.org/en/stable/tutorials/scripting/singletons_autoload.html), [FileAccess](https://docs.godotengine.org/en/stable/classes/class_fileaccess.html), and [JSON](https://docs.godotengine.org/en/stable/classes/class_json.html).
