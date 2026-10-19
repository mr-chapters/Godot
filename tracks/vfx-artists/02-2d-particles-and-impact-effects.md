# Chapter 2 — 2D Particles and Impact Effects

**Mission:** create a reusable 2D effect scene that emits particles and cleans itself up safely.

## 1. Choose the right node

In Godot 4, GPUParticles2D is suitable for many particle effects and can render lots of particles efficiently on supported hardware. CPUParticles2D can be useful where CPU processing or compatibility requirements make sense. Start with the simpler option that fits your project and target devices.

## 2. Create a reusable burst

1. Create a new scene with GPUParticles2D as its root.
2. Assign a ParticleProcessMaterial.
3. Enable one-shot emission for a burst.
4. Set a short lifetime and a suitable amount.
5. Adjust direction, spread, initial velocity, gravity, scale, and colour.
6. Add a small texture or use a simple particle shape.
7. Preview in the editor and test at actual game scale.

Property names and editor layout may vary slightly by Godot version. Read the Inspector tooltips and current class reference when unsure.

## 3. Spawn the effect at an impact point

Example for a reusable effect scene assigned in the Inspector:

~~~gdscript
extends Node2D

@export var impact_effect: PackedScene

func spawn_impact(world_position: Vector2) -> void:
    if impact_effect == null:
        push_warning("Assign an impact effect scene first.")
        return

    var effect := impact_effect.instantiate() as Node2D
    if effect == null:
        push_warning("The impact scene root must inherit Node2D.")
        return

    get_tree().current_scene.add_child(effect)
    effect.global_position = world_position
~~~

The example assumes the current scene exists and the effect root is Node2D. If your scene tree uses a dedicated effects container, add the effect there instead. Configure one-shot particles so they finish and are freed; do not delete an effect immediately after emitting it.

## 4. Build a readable impact

Try a brief bright flash, a small expanding ring, and a few particles moving outward. Keep the peak short, then fade away. Make the effect large enough to read but small enough not to hide the target.

## Mini-mission

Create pickup sparkle, landing dust, and a hit burst as separate scenes. Use them in a test room.

## Checkpoint

- What is one-shot emission for?
- Why check that the effect scene has the expected root type?
- Why should you test at the actual gameplay scale?

**Boss challenge:** build a small reusable VFX library with consistent naming and a README describing how to spawn each effect.

**Further reading:** [GPUParticles2D](https://docs.godotengine.org/en/stable/classes/class_gpuparticles2d.html) and [CPUParticles2D](https://docs.godotengine.org/en/stable/classes/class_cpuparticles2d.html).
