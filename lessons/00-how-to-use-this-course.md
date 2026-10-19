# 00 — How to Use This Course

## What is GDScript?

GDScript is a programming language built for the Godot Engine. You use it to describe game behaviour: how a player moves, what happens when two objects collide, how an enemy reacts, or when a level changes.

Godot also provides an editor, a scene system, physics, audio, animation, and user-interface tools. GDScript lets you connect those pieces and define your game's rules.

## What you need

- A computer that can run [Godot](https://godotengine.org/download/).
- A text editor is optional; Godot includes a script editor.
- Patience to test small ideas. No previous coding experience is required.

Use the current stable **Godot 4.x** release for these lessons. Godot 3 tutorials can show different syntax and APIs.

## How each lesson works

Each chapter should contain:
- **Concept:** what the feature means and why it exists.
- **Example:** a small, focused snippet.
- **Walkthrough:** what each important line does.
- **Common mistakes:** errors beginners often make.
- **Practice:** tasks that require you to modify or extend the example.
- **References:** official documentation for deeper reading.

Don't treat code as magic. Ask yourself: What information enters this code? What changes? What result should happen? How could I test that?

## Your first practice project

Create a new project in Godot. Choose a simple name such as `GDScriptPractice`. Create a scene with a `Node` as its root, save it as `Main.tscn`, and set it as the main scene if prompted.

You will attach scripts to nodes as you move through the course. A script file usually ends in `.gd`.

## The most useful learning loop

1. Read a concept.
2. Predict what the example will do.
3. Run it.
4. Change one thing.
5. Run it again.
6. Explain the result in your own words.

If you get an error, that is part of learning. Read the message, find the named line, and check spelling, punctuation, indentation, node paths, and types.

## Check your understanding

Before moving on, make sure you can explain:
1. What GDScript is used for.
2. What role Godot plays besides running scripts.
3. Why typing and changing examples teaches more than only copying them.

**Official references:** [Introduction to Godot](https://docs.godotengine.org/en/stable/getting_started/introduction/index.html) · [GDScript overview](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/index.html)
