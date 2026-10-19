# 10 — Collections Practice: Inventory and Scores

This lesson combines arrays, dictionaries, loops, and functions into a small inventory model. It uses ordinary data and can run on a plain `Node`.

## Example

```gdscript
extends Node

var inventory: Array[String] = ["Potion", "Key"]
var scores: Dictionary = {
    "Nova": 120,
    "Kai": 95,
    "Mina": 210
}

func add_item(item_name: String) -> void:
    if not inventory.has(item_name):
        inventory.append(item_name)
        print(item_name + " added.")
    else:
        print(item_name + " is already in the inventory.")

func print_inventory() -> void:
    print("Inventory:")
    for item in inventory:
        print("- " + item)

func get_total_score() -> int:
    var total: int = 0
    for player_name in scores:
        total += scores[player_name]
    return total

func _ready() -> void:
    add_item("Map")
    add_item("Key")
    print_inventory()
    print("Combined score: ", get_total_score())
```

## Walkthrough

1. `inventory` is an ordered list of strings.
2. `scores` maps player names to integer scores.
3. `add_item` checks for duplicates before adding.
4. `print_inventory` loops over each item.
5. `get_total_score` visits each dictionary key and adds the corresponding score.
6. `_ready` calls the functions when the node is ready.

## Extend it

- Add a function that removes an item only if it exists.
- Add a function that checks whether a player has an item.
- Add a new player's score and check the total.
- Print a message when the inventory is empty.
- Decide how the code should behave if a score key is missing.

## Think like a programmer

Before changing the code, write down the expected result. Run it and compare the actual result with your prediction. If they differ, inspect the conditions and data step by step.

**Official reference:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
