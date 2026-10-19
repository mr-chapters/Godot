# Builders' Book — Chapter 2: Make the Level Fair and Readable

> **Mission:** design a route with a safe start, a challenge, a reward, and an exit.

## A level communicates without words
A bright doorway suggests a destination. A narrow bridge suggests caution. A line of coins can guide the player toward a platform. If every object has the same visual intensity, nothing stands out.

Use visual hierarchy:
1. **Primary:** player, route, immediate danger.
2. **Secondary:** rewards, switches, useful landmarks.
3. **Decoration:** mood and detail that do not compete with gameplay.

Try switching your final art off or replacing it with flat shapes. If the route becomes confusing, improve the layout.

## Plan five beats
1. **Spawn:** a safe place to learn.
2. **Teach:** a simple obstacle.
3. **Test:** a slightly harder version.
4. **Reward:** a collectible, shortcut, or satisfying view.
5. **Exit:** a recognizable finish.

This simple sequence introduces an idea, lets the player practise, then rewards them.

## Collision layers and masks
Collision layers describe what category an object belongs to; collision masks describe which layers it checks for. Choose a consistent project convention and document it.

| Object | Example layer | Example mask |
|---|---|---|
| Player | Player | World, enemies, pickups |
| Floor | World | Player, enemies |
| Pickup Area2D | Pickup | Player |
| Enemy | Enemy | World, player |

These names describe a design; the actual layer bit numbers depend on your project. For a pickup, also check Area2D monitoring, its CollisionShape2D, and whether the player's layer is included in the pickup's mask.

## Example: collect an item
Create a scene with Area2D root, Sprite2D, and CollisionShape2D. Connect the Area2D's `body_entered` signal to this script:

```gdscript
extends Area2D

signal collected

func _on_body_entered(body: Node2D) -> void:
    if body.is_in_group("player"):
        collected.emit()
        queue_free()
```

Add the player to a group named `player` using the Node dock's Groups tab. Connect the signal in the editor. This example announces collection and removes the pickup; a score manager can listen and update the score.

## Fairness and accessibility
- Do not rely on colour alone to distinguish safe and dangerous objects.
- Show hazards before they punish the player.
- Put checkpoints before long frustrating sequences.
- Test at the actual camera zoom and window size.
- Keep optional routes distinguishable from required paths.

## Mini-mission
Create a five-beat room using placeholder shapes. Add one pickup Area2D and an exit marker. Ask someone to play without explaining the route.

**Boss challenge:** use their hesitations to improve the layout, then retest it.

## Checkpoint
1. What does a collision mask determine?
2. Why use a group to identify the player?
3. Name the five level beats.
4. Why should hazards be readable before contact?

<details><summary>Answer key</summary>

1. Which collision layers the object checks for.
2. It avoids relying on a fragile node name or exact tree location.
3. Spawn, teach, test, reward, exit.
4. It gives players a fair chance to understand and respond.
</details>

**Next:** [Build once, reuse everywhere](03-reusable-scenes-and-tilemaps.md).
