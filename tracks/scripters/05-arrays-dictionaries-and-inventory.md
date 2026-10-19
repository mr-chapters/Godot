# Scripters' Book — Chapter 5: Collections and a Tiny Inventory

> **Mission:** store collected items and look them up by name without creating a separate variable for every item.

## 1. Why collections exist

Imagine a game with 40 items. Creating variables like `item_1`, `item_2`, and `item_3` quickly becomes hard to manage. A collection stores related values together.

An **Array** is an ordered list. A **Dictionary** stores key-value pairs.

```gdscript
var inventory: Array[String] = ["key", "potion", "coin"]
var item_counts: Dictionary = {
    "coin": 3,
    "potion": 1
}
```

Array positions start at index 0. `inventory[0]` is `"key"`. A dictionary lookup uses a key: `item_counts["coin"]` is 3.

## 2. Add, remove, and inspect items

```gdscript
var inventory: Array[String] = []

func add_item(item_name: String) -> void:
    inventory.append(item_name)
    print("Collected: ", item_name)

func remove_item(item_name: String) -> bool:
    if inventory.has(item_name):
        inventory.erase(item_name)
        return true
    return false
```

`append()` adds an item to the end. `has()` checks whether an item exists. `erase()` removes a matching value. The function returns true when it found and removed the item, otherwise false.

## 3. A dictionary-based stack count

```gdscript
var item_counts: Dictionary = {}

func add_item(item_name: String, amount: int = 1) -> void:
    var current_count: int = item_counts.get(item_name, 0)
    item_counts[item_name] = current_count + amount

func get_item_count(item_name: String) -> int:
    return int(item_counts.get(item_name, 0))
```

The dictionary's `get()` method returns the stored value or a fallback if the key does not exist. In this example, a missing item count is treated as zero. Use a clear rule for what should happen if an item count becomes negative; this example does not yet prevent that.

## 4. Iterate over a collection

```gdscript
for item_name in inventory:
    print("Inventory item: ", item_name)

for item_name in item_counts:
    print(item_name, ": ", item_counts[item_name])
```

The first loop visits each value in the array. The second visits dictionary keys. Do not change a collection unpredictably while looping over it; if you need to remove many entries, collect the entries to remove first or use an approach designed for safe modification.

## 5. A simple inventory test

Attach this to a Node and run the scene:

```gdscript
extends Node

var inventory: Array[String] = ["key", "potion"]

func _ready() -> void:
    inventory.append("coin")
    print("Items: ", inventory)
    print("Has key: ", inventory.has("key"))

    if inventory.has("potion"):
        inventory.erase("potion")

    print("After using potion: ", inventory)
```

You should see the key and coin remain after the potion is removed.

## 6. Design questions

- Can the player carry duplicate items?
- Does an item have a count, a unique identity, or both?
- Can the inventory be empty?
- What happens when it reaches its capacity?
- Should key items be removable?
- Does the game save the inventory?

Answer these questions before designing a complicated inventory system.

## 7. Mini-mission

Create an inventory that can hold a key, three potions, and coins. Print a clear summary. Prevent using a potion if the player has zero potions.

**Boss challenge:** make a function `use_item(item_name)` that returns whether the action succeeded and updates the stored quantity safely.

## 8. Checkpoint

1. When should you use an Array?
2. When is a Dictionary useful?
3. What does `get("coin", 0)` do if coin is missing?
4. Why should inventory rules be decided before implementation?

<details><summary>Answer key</summary>

1. For an ordered sequence of values.
2. When values are retrieved using meaningful keys.
3. It returns the fallback value 0.
4. Rules determine the data structure and edge cases the code must handle.
</details>
