# ✨ VFX Artists' Book — Make Game Actions Feel Powerful

Learn how to build visual effects for 2D and 3D Godot games: impact flashes, particles, trails, explosions, magic, environmental effects, screen feedback, and performance-friendly polish.

## Chapters

1. [VFX Fundamentals and Visual Language](01-vfx-fundamentals.md) — timing, shape, contrast, anticipation, impact, and follow-through.
2. [2D Particles and Impact Effects](02-2d-particles-and-impact-effects.md) — GPUParticles2D, bursts, sparks, dust, and reusable scenes.
3. [Shaders, Glow, and Screen Effects](03-shaders-glow-and-screen-effects.md) — CanvasItem shaders, gradients, glow, and restrained post-processing.
4. [3D Particles and World Effects](04-3d-particles-and-world-effects.md) — GPUParticles3D, trails, fog, sparks, and spatial placement.
5. [VFX Timing, Animation, and Gameplay Feedback](05-timing-animation-and-feedback.md) — animation curves, hit feedback, readability, and accessibility.
6. [Optimization, Reuse, and VFX Portfolio](06-optimization-reuse-and-portfolio.md) — pooling, budgets, testing, and delivery.

## Suggested workflow

**Reference → rough timing → simple shapes → gameplay test → polish → performance check.** Effects should support gameplay, not hide it. Build small effects first and make them readable at the actual gameplay camera distance.

## Tools and references

- [Godot particle systems](https://docs.godotengine.org/en/stable/tutorials/3d/particles/index.html)
- [CanvasItem shaders](https://docs.godotengine.org/en/stable/tutorials/shaders/shader_reference/canvas_item_shader.html)
- [Godot shading language](https://docs.godotengine.org/en/stable/tutorials/shaders/shader_reference/shading_language.html)
- [Kenney assets](https://kenney.nl/assets) — check each pack's licence.

## Graduation challenge

Create a reusable effect pack with a pickup sparkle, landing dust, hit flash, and one signature ability effect. Test every effect against real gameplay, document how to instantiate it, and list any performance or visual limitations.
