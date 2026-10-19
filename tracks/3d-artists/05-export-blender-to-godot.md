# Chapter 5 — Export from Blender to Godot

**Mission:** deliver a model that imports with the expected size, orientation, materials, and dependencies.

## Keep the source and game asset separate

Keep the editable .blend source file in a sensible source folder if your workflow requires it. Export a game-ready version to the Godot project. Do not overwrite the only editable source with an exported copy.

Common exchange formats include glTF/GLB and FBX. For a straightforward Blender-to-Godot workflow, glTF/GLB is often a practical starting point. Confirm the capabilities and limitations of the format you choose in current documentation.

## Before export

- Give objects meaningful names.
- Check dimensions, origin, rotation, and scale.
- Remove hidden objects that should not be exported.
- Confirm materials and texture dependencies.
- Decide whether animation should be included.
- Export a small test before exporting a whole asset library.

## After import in Godot

Open the imported scene and check:
- Is it facing the intended direction?
- Is its scale correct beside a known-size object?
- Did materials and textures import?
- Does animation play if expected?
- Does collision need to be added separately?
- Does the asset look correct under the game's lighting?

An import succeeding does not guarantee the result is correct.

## Troubleshooting table

| Problem | First things to check |
|---|---|
| Model is too large or small | Blender dimensions, export scale, Godot node scale |
| Model faces the wrong way | Forward/up axis conventions and export settings |
| Texture is missing | File paths, exported dependencies, material references |
| Pivot behaves strangely | Object origin and transform setup |
| Model looks too dark | Material settings, normals, scene lighting |
| Physics feels wrong | Collision shape, scale, and physics setup |

Change one likely cause at a time so you know which fix worked.

## Asset handoff note

- **Asset:** wooden_crate
- **Source:** wooden_crate.blend
- **Export:** wooden_crate.glb
- **Intended scale:** compare with the project's standard character height
- **Textures:** list files or state that none are required
- **Collision:** simple box collision expected
- **Licence:** include source and attribution requirements
- **Known issues:** list anything the integrating developer should know

## Mini-mission

Export one crate, import it into a new Godot project, place it next to a CharacterBody3D, and verify its scale and orientation. Repeat after changing one material.

## Checkpoint

1. Why keep a source file?
2. Why inspect an imported model in Godot?
3. Why document licences and dependencies?

**Boss challenge:** deliver a three-prop set with consistent scale, clean names, working materials, and a handoff note for another developer.

**Further reading:** [Godot importing 3D scenes](https://docs.godotengine.org/en/stable/tutorials/assets_pipeline/importing_3d_scenes/index.html), [Blender manual](https://docs.blender.org/manual/en/latest/), and [glTF specification](https://www.khronos.org/gltf/).
