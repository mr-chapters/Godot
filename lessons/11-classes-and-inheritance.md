# 11 — Classes, Inheritance, and Script Structure

Godot uses objects and classes to organise behaviour. A node is an object with a type, properties, and methods. A script attached to a node can extend a built-in Godot class or another script class.

## Inheritance

```gdscript
extends Node2D

func _ready() -> void:
    print("This node has Node2D behaviour.")
```

`extends Node2D` means the script inherits the behaviour of `Node2D`. It can use inherited methods and properties, such as its 2D transform.

Choose a base class based on what the object needs to do: `Node` for general organisation, `Node2D` for a 2D transform, or `CharacterBody2D` for a physics-driven 2D character.

## Reusable data classes

You can define a named class using `class_name` so other scripts can reference it:

```gdscript
# health_data.gd
class_name HealthData
extends RefCounted

var current: int
var maximum: int

func _init(max_health: int = 100) -> void:
    maximum = max_health
    current = maximum
```

Save this script as `health_data.gd`. After Godot registers the global class, another script can create an instance:

```gdscript
var health_info: HealthData

func _ready() -> void:
    health_info = HealthData.new(150)
    print(health_info.current)
```

This is a reusable data object, not a scene node. `RefCounted` is useful for lightweight objects that do not need to live in the scene tree.

## Composition is another option

A scene can contain several child nodes, and a script can hold references to other objects. This is composition: combining smaller parts to build behaviour.

Use inheritance when there is a genuine "is a kind of" relationship. Use composition when an object needs to work with separate systems or components. Neither approach is automatically best for every problem.

## Common mistakes

- Extending a class that lacks the behaviour you need.
- Expecting a `RefCounted` object to appear in the scene tree.
- Referencing a global class before its script is saved and registered.
- Building a deep inheritance hierarchy when a helper object or child node would be clearer.

## Practice

1. Explain why a `CharacterBody2D` script differs from a `Node` script.
2. Create a data class for a player's name and score.
3. Create two instances and confirm their values are independent.
4. Decide whether an inventory should inherit from a character or be a separate object used by the character. Explain why.

**Official references:** [GDScript basics](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_basics.html) · [RefCounted](https://docs.godotengine.org/en/stable/classes/class_refcounted.html)
