# 09 — Arrays and Dictionaries

Games store collections such as inventories, enemy lists, scores, and settings. GDScript's arrays and dictionaries help organise this data.

## Arrays: ordered values

An array stores items in order. Its first item is at index `0`.

```gdscript
var inventory: Array[String] = ["Potion", "Key", "Map"]

func _ready() -> void:
    print(inventory[0]) # Potion
    print(inventory.size()) # 3
    inventory.append("Coin")
    inventory.erase("Map")
    print(inventory)
```

Useful operations include `append(value)`, `size()`, `has(value)`, `erase(value)`, and `remove_at(index)`. Always make sure an index exists before reading or removing an element.

## Dictionaries: key-value pairs

A dictionary associates keys with values:

```gdscript
var player_stats: Dictionary = {
    "health": 100,
    "coins": 0,
    "player_name": "Nova"
}

func _ready() -> void:
    print(player_stats["health"])
    player_stats["coins"] += 5
    print(player_stats.get("level", 1))
```

Use `get(key, default)` when a key might be absent and you want a fallback. Directly accessing a missing key can cause an error.

## Which should you choose?

Use an array when order matters or you need to process every item. Use a dictionary when you need to look up a value by a meaningful key.

Typed containers can make intent clearer:

```gdscript
var scores: Array[int] = [100, 250, 175]
var prices: Dictionary = {"potion": 10, "key": 25}
```

## Common mistakes

- Assuming arrays start at index 1.
- Reading an index outside the array's bounds.
- Assuming a dictionary always contains a particular key.
- Removing array elements during iteration without considering how indices shift.
- Adding a value of the wrong type to a typed array.

## Practice

1. Create an inventory with four items, then add and remove one.
2. Print the second item in the inventory.
3. Create a dictionary for health, coins, and level, then update coins.
4. Read a missing dictionary key with a safe default.
5. Loop through an integer array and count values greater than 10.

**Official reference:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html)
