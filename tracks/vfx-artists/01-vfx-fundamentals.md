# Chapter 1 — VFX Fundamentals and Visual Language

**Mission:** create effects that make actions readable and satisfying without covering the gameplay.

## 1. What a game effect communicates

A visual effect can communicate impact, danger, reward, movement, magic, weather, or the direction of an action. Before drawing particles, decide what the player should understand. A healing effect should not look exactly like damage; a dangerous projectile should be visible against its background.

## 2. The four-part impact

Many readable action effects use a simple rhythm:
1. **Anticipation:** a brief wind-up, glow, or growing shape.
2. **Impact:** the strongest, clearest frame.
3. **Follow-through:** sparks, fragments, a ring, or a short trail.
4. **Dissipation:** the effect fades and leaves the screen clear.

Not every effect needs all four stages, but timing and contrast usually matter more than particle count.

## 3. Shape language

Sharp, fast shapes can suggest danger or cutting; round soft shapes can suggest healing, bubbles, or gentle magic. These are design conventions, not universal rules. Keep your project's visual language consistent and make important effects distinct from each other.

## 4. Start with a reference and a timing sketch

Watch an effect at normal speed, then slow it down if useful. Note its start, peak, and end. Create a rough version with simple circles or lines before adding textures.

## 5. Mini-mission

Make three tiny effects: a positive pickup, a damage impact, and a movement burst. Ensure they are distinguishable in a crowded scene and in grayscale.

## Checkpoint

- What does anticipation do?
- Why can too many particles make an effect worse?
- How can two effects remain distinguishable without relying only on colour?

**Boss challenge:** create a signature effect for your own game and write one sentence explaining what it communicates.

**Diagram — effect timing**

~~~text
Intensity
  high             /  IMPACT
                  /  ____
                 /        ___ DISSIPATION
  low   ________/ 
        ANTICIPATION  FOLLOW-THROUGH  → time
~~~

**Further reading:** [Godot particles](https://docs.godotengine.org/en/stable/tutorials/3d/particles/index.html).
