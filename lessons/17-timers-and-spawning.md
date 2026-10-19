# 17 — Timers and Spawning

Timers let gameplay wait for a duration without writing a blocking loop. They are useful for cooldowns, enemy spawning, temporary effects, and countdowns.

## Use a Timer node

Add a `Timer` child to a node. Set its `Wait Time`, decide whether it should `One Shot`, and connect its `timeout` signal. You can also control it from code.

```gdscript
extends Node

@onready var spawn_timer: Timer = $SpawnTimer

func _ready() -> void:
    spawn_timer.timeout.connect(_on_spawn_timer_timeout)
    spawn_timer.start()

func _on_spawn_timer_timeout() -> void:
    print("Time to spawn something.")
```

This assumes a child named `SpawnTimer` exists. Configure the Timer's wait time in the Inspector, or set `spawn_timer.wait_time` before calling `start()`.

## Restarting a one-shot timer

A one-shot timer stops after it times out. If you want it to repeat, either turn off **One Shot** or start it again from the timeout callback. Choose the behaviour that matches your design.

## Spawning a scene

A reusable enemy scene can be loaded as a PackedScene and instantiated:

```gdscript
extends Node2D

@export var enemy_scene: PackedScene

func spawn_enemy(at_position: Vector2) -> void:
    if enemy_scene == null:
        push_warning("Assign an enemy scene in the Inspector.")
        return

    var enemy := enemy_scene.instantiate()
    add_child(enemy)
    enemy.global_position = at_position
```

Assign an enemy scene to the exported `enemy_scene` property in the Inspector. The scene should have a root node with a global position, such as `Node2D` or a subclass. In larger games, add spawned objects under a dedicated container node instead of directly under the level root.

## Avoid spawning without limits

A timer that spawns something forever can create too many nodes. Decide when spawning should stop, how many enemies can exist, and how the game handles a missing PackedScene.

## Practice tasks

1. Make a Timer print a message every two seconds.
2. Change it to one-shot and explain the difference.
3. Create a simple enemy scene and spawn one instance.
4. Add a maximum active enemy count to prevent unlimited spawning.

**Official references:** [Timer](https://docs.godotengine.org/en/stable/classes/class_timer.html) · [Instantiating scenes](https://docs.godotengine.org/en/stable/tutorials/scripting/nodes_and_scene_instances.html)
