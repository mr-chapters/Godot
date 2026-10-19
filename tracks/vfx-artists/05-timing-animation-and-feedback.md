# Chapter 5 — VFX Timing, Animation, and Gameplay Feedback

**Mission:** make feedback clear, quick, and consistent with the action that caused it.

## 1. Timing often matters more than detail

An effect with a clear start, peak, and end can feel stronger than a complicated effect with poor timing. Use AnimationPlayer, Tween, or particle properties to animate scale, opacity, colour, and movement. Pick the tool that best fits the task and project version.

## 2. Connect feedback to gameplay events

Examples:
- Collectible acquired → sparkle plus score change.
- Player takes damage → brief hit flash and health update.
- Heavy landing → dust puff and landing sound.
- Ability ready → subtle icon or effect.
- Enemy defeated → short effect that does not hide the next threat.

Keep the visual feedback connected to a clear game event. Avoid effects that imply damage or reward when nothing happened.

## 3. Signal-based design

A reusable effect should not need to know every detail of the gameplay system. Let the gameplay event trigger the effect through a function or signal, and pass the position or type of effect it needs.

~~~mermaid
flowchart LR
    A[Gameplay event] --> B[Effect request]
    B --> C[Spawn VFX scene]
    C --> D[Play particles or animation]
    D --> E[Finish and clean up]
~~~

## 4. Accessibility and options

Consider options for reducing screen shake, flashes, intense glow, and rapidly moving effects. Never rely on a flash alone to communicate an important event; pair it with sound, animation, iconography, or text where appropriate.

## Mini-mission

Add a hit flash and a small knockback effect to a test target. Make sure the target's health changes once, even if several visual particles appear.

## Checkpoint

- Why should VFX be triggered by a real gameplay event?
- What is the difference between a gameplay result and its visual feedback?
- Name two options that can improve comfort.

**Boss challenge:** build a small ability from anticipation through impact to fade-out. Make sure it remains understandable when other enemies and UI are visible.

**Further reading:** [AnimationPlayer](https://docs.godotengine.org/en/stable/classes/class_animationplayer.html) and [Tween](https://docs.godotengine.org/en/stable/classes/class_tween.html).
