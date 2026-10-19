# Chapter 2 — Modelling and Game Scale

**Mission:** make models that read clearly, export predictably, and do not waste effort on invisible detail.

## Silhouette before detail

A silhouette is an object's outline. At small screen sizes, the outline often communicates more than surface detail. Compare your model in solid shading and from the gameplay camera. If its purpose is unclear, adjust its proportions before adding textures.

## Apply transforms intentionally

Objects have location, rotation, and scale transforms. Non-uniform or unapplied scale can complicate modifiers, physics, and export. Before exporting, check dimensions, origin, rotation, and scale. Apply transforms when your workflow calls for it, then verify the exported result.

## Topology basics

- **Vertices** are points.
- **Edges** connect points.
- **Faces** form surfaces.
- **Topology** is how these elements are arranged.

Game props do not always need dense geometry. Add loops where the silhouette or deformation needs them. Avoid invisible complexity that increases file size without improving the game.

## Origins and pivots

The origin affects how an object is positioned and rotated. A door usually needs a hinge-like pivot; a spinning pickup may need its pivot near its centre. Choose an origin that matches how the object will be placed or animated.

## Collision is not the render mesh

Visual geometry and collision geometry solve different problems. A decorative model may need a simpler collision shape for reliable, efficient physics. Do not assume every visible detail should collide.

## Mini-mission

Make a low-detail barrel. Place its origin sensibly, test its dimensions against a player character, and create a simpler collision shape in Godot.

## Checkpoint

- Why is silhouette important?
- What is an object's origin used for?
- Why might collision use fewer shapes than the rendered model?

**Boss challenge:** create three props that share a consistent scale and visual style. Place them next to a player character in Godot and adjust any prop that feels too large or small.

**Common mistakes:** modelling details before checking size, forgetting the origin, and using complicated visual geometry as collision without considering performance.

**Further reading:** [Blender modelling documentation](https://docs.blender.org/manual/en/latest/modeling/index.html) and [Godot physics introduction](https://docs.godotengine.org/en/stable/tutorials/physics/physics_introduction.html).
