# Chapter 4 — 3D Particles and World Effects

**Mission:** create spatial effects that fit the world and remain visible from the game's camera.

## 1. Start with GPUParticles3D

Create a GPUParticles3D node, assign a ParticleProcessMaterial, set a sensible amount and lifetime, and preview it in a test scene. Use emission shapes to control where particles originate. Set gravity, spread, direction, initial velocity, and scale to match the effect.

## 2. Match the effect to the world

A spark should originate at the contact point; dust should sit near the ground; smoke should rise according to the intended world style. Check orientation and transforms, especially when spawning effects from rotated enemies or weapons.

## 3. Trails and moving effects

Trails can show motion, attack direction, or projectile paths. Keep them short enough that old positions do not obscure current action. If an effect follows a moving object, decide whether it should remain attached or be left behind in world space when the object moves away.

## 4. Fog, weather, and ambience

World effects such as fog, rain, dust, and floating particles create atmosphere. They can also obscure enemies and landmarks. Keep critical navigation information visible and test the scene at the farthest camera distance.

## 5. Mini-mission

Create a 3D impact burst, a rising smoke effect, and an ambient floating-particle effect. Compare their readability from the player's actual camera.

## Checkpoint

- What does an emission shape control?
- When should a trail remain attached to its source?
- How can fog affect gameplay readability?

**Boss challenge:** create a reusable 3D ability effect with a clear origin, brief peak, and clean fade-out.

**Diagram — spatial impact**

~~~text
        sparks ↑ ↗
      ↖   |   ↗
         [HIT]  ← impact point
       dust ↓ ↓
-------------------- ground
~~~

**Further reading:** [Godot 3D particles](https://docs.godotengine.org/en/stable/tutorials/3d/particles/index.html) and [GPUParticles3D](https://docs.godotengine.org/en/stable/classes/class_gpuparticles3d.html).
