# Chapter 6 — Optimization, Reuse, and VFX Portfolio

**Mission:** make effects reusable, measurable, and easy for another developer to integrate.

## 1. Reuse scenes

Create a separate scene for each effect family and give it a clear name. Export PackedScene references in the systems that spawn them instead of hard-coding file paths in many scripts. Keep effect scenes focused: an effect should not own unrelated score, health, or inventory logic.

## 2. Clean up after playback

One-shot particles need time to finish. Use a deliberate cleanup strategy, such as a small controller that waits until the effect is finished and then frees its node, or an animation that calls a cleanup method at the correct time. Test the cleanup path so effects do not accumulate invisibly in the scene tree.

## 3. Profile before optimizing

Too many particles, overdraw from large transparent sprites, expensive shaders, dynamic lights, and excessive screen effects can hurt performance. Measure on target hardware. Lower particle counts, reduce lifetime or size, simplify shader work, and avoid spawning effects that are off-screen when appropriate.

## 4. Consistency and naming

Use names such as vfx_pickup_sparkle, vfx_hit_small, or vfx_landing_dust. Store effect scenes in a predictable folder. Include a note on scale, expected parent, lifetime, and whether the effect uses audio or screen feedback.

## 5. Portfolio presentation

For each effect, show:
- A short clip or GIF in the actual game scene.
- The effect's purpose and the event that triggers it.
- What nodes, particles, or shaders it uses.
- Any performance choices or accessibility alternatives.
- Credits and licences for textures, sounds, or reference assets.

## Mini-mission

Audit a test scene after repeatedly triggering an effect. Check that nodes are cleaned up and performance remains stable.

## Checkpoint

- Why separate effects into reusable scenes?
- What is overdraw?
- What belongs in a good effect handoff?

**Boss challenge:** deliver a four-effect pack, a demo scene, clear instructions, and a short portfolio clip. Ask another developer to integrate one effect using only your README.

**Further reading:** [Godot profiler](https://docs.godotengine.org/en/stable/tutorials/scripting/debug/the_profiler.html) and [GPUParticles2D](https://docs.godotengine.org/en/stable/classes/class_gpuparticles2d.html).
