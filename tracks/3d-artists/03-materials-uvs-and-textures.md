# Chapter 3 — Materials, UVs, and Textures

**Mission:** make a model's surface communicate its material without making the asset unnecessarily expensive.

## Material versus texture

A **material** describes how a surface responds to light. A **texture** is image data that can provide colour, roughness, normal information, or other surface properties. A material can use no image textures at all.

A simple stylised prop can often use a small colour palette and a few material values. Realistic assets may need more detailed texture maps.

## UV coordinates

UVs map points on a 3D surface to positions in a 2D image. Imagine unfolding a cardboard box into a flat net: the net is similar to a UV layout. Seams are sometimes necessary. Place them where they are less visible and avoid accidental stretching.

## A practical material checklist

- Is the main colour readable under the game's lighting?
- Is roughness appropriate for the surface?
- Are important details visible from the expected camera distance?
- Are texture sizes appropriate for the asset's screen size?
- Are all external texture files included in the project?

Do not use detail to compensate for a weak shape. Check the silhouette first.

## Keep a consistent art direction

Choose a few rules: realistic or stylised, smooth or angular, muted or saturated, clean or weathered. Reuse a palette and material approach across assets so the world feels like one game rather than a collection of unrelated models.

## Mini-mission

Create one metal-like material and one wood-like material for the same crate. Compare them in Godot's actual scene lighting and ensure the crate remains readable.

## Checkpoint

1. How is a material different from a texture?
2. What do UV coordinates do?
3. Why should materials be tested in the game scene?

**Boss challenge:** make three materials that belong to one coherent environment. Include a note about texture files and their licence.

**Further reading:** [Blender materials](https://docs.blender.org/manual/en/latest/render/materials/index.html), [UV mapping](https://docs.blender.org/manual/en/latest/modeling/meshes/uv/index.html), and [Godot materials](https://docs.godotengine.org/en/stable/tutorials/3d/standard_material_3d.html).
