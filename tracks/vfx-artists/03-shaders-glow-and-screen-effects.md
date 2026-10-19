# Chapter 3 — Shaders, Glow, and Screen Effects

**Mission:** use simple shader effects to add style while preserving readability and performance.

## 1. What is a shader?

A shader is a small program that controls how graphics are drawn. A CanvasItem shader affects 2D items such as sprites and UI elements. A shader can tint a sprite, make a dissolve, add a moving highlight, or distort an image.

## 2. Your first tint shader

Attach a ShaderMaterial to a Sprite2D and use a CanvasItem shader:

~~~glsl
shader_type canvas_item;

uniform vec4 tint_color : source_color = vec4(1.0, 0.5, 0.2, 1.0);

void fragment() {
    COLOR *= tint_color;
}
~~~

The shader multiplies the sampled sprite colour by a configurable tint. If the sprite is white, the tint is easy to see; if it already has strong colours, the result combines with them.

## 3. Glow and bloom

Glow can make bright areas appear to spill light into nearby pixels. In Godot, glow is configured through the environment and renderer settings appropriate to your project. Exact options differ by renderer and version. Use it selectively: too much glow can blur UI text, hide silhouettes, and reduce contrast.

## 4. Screen shake and flashes

Small screen shake or a brief damage flash can reinforce an impact, but avoid using intense or constant motion. Provide settings where practical, keep the duration short, and test whether the effect makes aiming, reading, or navigation harder.

## 5. Mini-mission

Add a configurable tint to a pickup, then create a short dissolve or glow treatment. Compare the effect with glow disabled and enabled.

## Checkpoint

- What does a CanvasItem shader affect?
- Why might glow make a game harder to read?
- What should you consider before adding screen shake?

**Boss challenge:** create three shader presets for a game: a safe pickup, a rare reward, and a temporary damage state. Ensure each stays readable over both dark and bright backgrounds.

**Diagram — render feedback pipeline**

~~~text
Sprite / effect
      ↓
Material or shader
      ↓
Scene composition
      ↓
Optional environment glow
      ↓
Final screen
~~~

**Further reading:** [CanvasItem shaders](https://docs.godotengine.org/en/stable/tutorials/shaders/shader_reference/canvas_item_shader.html) and [Godot shading language](https://docs.godotengine.org/en/stable/tutorials/shaders/shader_reference/shading_language.html).
