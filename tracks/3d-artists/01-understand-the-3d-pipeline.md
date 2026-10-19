# Chapter 1 — Understand the 3D Pipeline

**Mission:** take an idea from reference to a model that works inside a playable game.

## The pipeline in plain English

1. **Reference:** gather images and decide what must be recognisable.
2. **Blockout:** build the simplest shapes that establish size and silhouette.
3. **Model:** refine only parts visible or important to gameplay.
4. **UV and materials:** map textures and define surface appearance.
5. **Export:** move the asset and dependencies into the game project.
6. **Integrate:** test scale, orientation, materials, collision, and lighting in Godot.
7. **Revise:** fix problems visible in the actual game, not only in Blender.

Skipping integration can leave you with a beautiful asset that is too large, faces the wrong way, or is difficult to use.

## Start with a blockout

In Blender, add cubes, cylinders, and other primitives to represent the main masses. Use a camera angle similar to the game's view. Ask:
- Can I recognise the object from a distance?
- Does its outline differ from nearby objects?
- Does it fit through the doorway or onto the platform?
- Does it distract from important gameplay objects?

Do not begin with tiny bolts and scratches. First make the large shapes work.

## Think about the player camera

A first-person prop, a third-person character, and a distant background building have different requirements. The camera determines which details are visible and how much geometry is useful. Details that cannot be seen during normal play may not be worth modelling.

## Plan your deliverables

A handoff should include source files when appropriate, exported model and textures, consistent object names, intended scale and orientation, collision or gameplay notes, licence and attribution requirements, and a screenshot in the target game.

## Mini-mission

Model a simple crate from a cube. Make two variants using a few shape changes. Export all three and place them in one Godot test scene.

## Checkpoint

1. Why test a blockout before detailed modelling?
2. Why does the target camera affect modelling decisions?
3. What information helps another developer use your asset?

**Boss challenge:** create a small prop that is readable from the game's intended camera distance and provide a handoff note.

**Further reading:** [Blender manual](https://docs.blender.org/manual/en/latest/) and [Godot 3D introduction](https://docs.godotengine.org/en/stable/tutorials/3d/introduction_to_3d.html).
