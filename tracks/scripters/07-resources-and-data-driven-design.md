# Chapter 7 — Resources and Data-Driven Design

**Mission:** stop hard-coding every weapon, enemy, and collectible into separate scripts. Separate what an object *is* from how it behaves.

## Why data-driven design?

If every weapon's name, damage, cooldown, and icon are written directly into one long script, balancing is slow and mistakes are easy. A custom Resource lets you store reusable design data in an asset that can be edited in the Inspector.

## Create a resource type

Create a script named weapon_data.gd:

~~~gdscript
extends Resource
class_name WeaponData

@export var display_name: String = "Starter Blaster"
@export_range(1, 500, 1) var damage: int = 10
@export_range(0.05, 10.0, 0.05) var cooldown: float = 0.5
@export var projectile_scene: PackedScene
~~~

Attach no node to this script. It defines a resource type. In the FileSystem dock, create a resource of type WeaponData, save it as starter_blaster.tres, and set its exported values in the Inspector.

- class_name makes the custom type available in the editor.
- @export exposes a value in the Inspector.
- @export_range adds a constrained numeric control.
- PackedScene can hold a scene that will be instantiated later.

## Read the resource

~~~gdscript
extends Node
class_name Weapon

@export var data: WeaponData

func get_damage() -> int:
    if data == null:
        push_warning("WeaponData has not been assigned.")
        return 0
    return data.damage
~~~

Assign the resource to the data property in the Inspector. This example reads damage; it does not yet fire a projectile.

## Important resource behaviour

Resources are commonly shared. If two nodes reference the same resource and one changes its data at runtime, both may observe that change. Treat design data as read-only during play unless sharing is intentional. For per-instance mutable state, duplicate the resource or store that state on the node.

## Mini-mission

1. Make PotionData with a name, healing amount, and icon texture.
2. Create two potion resources with different values.
3. Make a consumer script that reads the healing amount.
4. Add a warning for a missing resource.
5. Explain which values belong in shared data and which belong on a living player.

## Checkpoint

- Why use a Resource instead of duplicate constants?
- What does @export do?
- Why be careful about changing a shared resource at runtime?

**Boss challenge:** create three EnemyData resources with different names, maximum health, movement speed, and contact damage. One enemy scene should read the assigned resource instead of needing a different script for every enemy.

**Common mistakes:** forgetting to assign the resource, assuming a Resource is a Node, and mutating shared design data as if it were unique per enemy.

**Further reading:** [Godot resources](https://docs.godotengine.org/en/stable/tutorials/scripting/resources.html) and [GDScript exports](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_exports.html).
