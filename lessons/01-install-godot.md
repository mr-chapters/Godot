# 01 — Install Godot and Understand the Editor

## 1. Download the engine

Download Godot from the [official download page](https://godotengine.org/download/). Choose the standard Godot 4 release for your operating system. Use the .NET edition only if you specifically plan to write C# as well; it is not required for GDScript.

Godot is free and open source. Follow the download page's instructions for your operating system.

## 2. Create a project

1. Open Godot.
2. In the Project Manager, choose **Create**.
3. Give the project a clear name such as `FirstGDScriptProject`.
4. Choose an empty folder for it.
5. Select the renderer suitable for your machine; the default is usually fine for learning.
6. Create and open the project.

A Godot project folder contains a `project.godot` file and the assets and scenes you add. Keep your project files together so Godot can find them.

## 3. Learn the main editor areas

- **Scene dock:** the nodes belonging to the currently open scene.
- **FileSystem dock:** project files, including scripts, images, sounds, and scenes.
- **Inspector:** properties of the selected node or resource.
- **Viewport:** visual workspace for 2D or 3D scenes.
- **Script editor:** where you write and read GDScript.
- **Output / Debugger:** messages, errors, warnings, and debugging tools.

Panels can move between layouts and versions. Focus on what each area does rather than memorising its exact position.

## 4. Make a tiny scene

1. Create a new scene.
2. Choose `Node` as the root.
3. Save it as `Main.tscn`.
4. Press **Run Current Scene** to test it.

A scene is a reusable collection of nodes arranged in a tree. Even an empty scene helps you learn how Godot organises a project.

## Practice tasks

- Create a project called `GDScriptLab`.
- Create and save a scene named `Main.tscn`.
- Find the `project.godot` file in the FileSystem dock.
- Identify the Scene dock, Inspector, Script editor, and Output panel.

## Common mistakes

- Saving a scene outside the project folder and then losing track of it.
- Following a Godot 3 tutorial while using Godot 4.
- Assuming a scene is the same thing as a script. A scene organises nodes; a script defines behaviour.

**Official references:** [Editor introduction](https://docs.godotengine.org/en/stable/getting_started/introduction/ Godot_editor.html) · [Step-by-step](https://docs.godotengine.org/en/stable/getting_started/step_by_step/index.html)
