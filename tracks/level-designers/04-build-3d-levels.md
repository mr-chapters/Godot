# Chapter 4 — Build 3D Levels

**Mission:** assemble a readable 3D level from reusable pieces and test its movement, camera, and collisions.

## 1. Start with modular pieces

A modular kit is a set of pieces designed to fit together: floor sections, walls, corners, door frames, stairs, platforms, and trim. Agree on a grid size and pivot conventions before making many assets. Consistency makes assembly faster.

## 2. Use simple geometry first

Use boxes and ramps to block out the route. Check door height, corridor width, platform distance, jump height, camera clipping, and whether the player can see important destinations. Replace the blockout with final art only after the route works.

## 3. Grid snapping

Snapping helps walls and floors align, but do not let the grid replace judgement. Check seams, overlapping surfaces, and tiny gaps. For organic terrain, a strict grid may not be the right tool.

## 4. Terrain and verticality

Height changes can create exploration and useful landmarks. Make climbs readable and provide safe places to understand a new movement mechanic. If a fall is dangerous, communicate the risk through shape, framing, animation, sound, or consistent visual language.

## 5. Collisions and navigation

Render meshes and collision shapes are different. Use simple collision where possible and test stairs, slopes, narrow spaces, moving platforms, and doorways with the real controller. If using NavigationRegion3D for AI, bake and inspect navigation data, then test whether agents can actually reach their destinations.

## Mini-mission

Build a small 3D courtyard from primitive shapes: entrance, central landmark, two routes, one raised platform, and exit. Test movement and camera behaviour before adding textures.

## Checkpoint

1. Why make modular pieces?
2. What does grid snapping help with?
3. Why test with the actual character controller?

**Boss challenge:** make a small 3D arena with a clear main route, one optional raised route, and a landmark visible from the entrance.

**Diagram — modular room plan**

~~~text
+-----------+-----------+
| Start     | Side room |
|           | Reward    |
+-----+-----+-----+-----+
      | Central hall   |
      | Landmark       |
+-----+----------------+
| Exit / next area     |
+----------------------+
~~~

**Further reading:** [Godot 3D](https://docs.godotengine.org/en/stable/tutorials/3d/index.html) and [Navigation overview](https://docs.godotengine.org/en/stable/tutorials/navigation/navigation_introduction_3d.html).
