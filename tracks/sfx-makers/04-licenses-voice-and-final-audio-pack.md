# SFX Makers' Book — Chapter 4: Build a Release-Ready Audio Pack

> **Mission:** deliver a small audio folder another developer can use without guessing what each file is or whether it is allowed in the game.

## 1. Treat licensing as part of production

For every sound you did not create yourself, record:
- the asset title,
- the creator,
- the original source URL,
- the licence shown for that specific file,
- any attribution text required,
- the date you checked the licence.

Asset packs can contain files with different terms. Never assume that all audio on a platform shares the same licence. If the terms are unclear, choose another asset or ask the creator.

## 2. Voice recordings

If you record voice:
- get permission from the person being recorded;
- explain where the voice may be used;
- record in a quiet environment;
- capture a short test before a long session;
- keep source recordings organised;
- remove accidental private information before sharing a build.

Do not use someone's voice to impersonate them or suggest they endorsed something they did not endorse.

## 3. Folder layout

A clean audio folder might look like:

```text
audio/
├── music/
│   ├── exploration_loop.ogg
│   └── danger_loop.ogg
├── sfx/
│   ├── coin_pickup.wav
│   ├── player_jump.wav
│   └── damage_hit.wav
└── README.md
```

Use a README to record source and licence details. Include attribution exactly as required by the asset's licence.

## 4. Quality-control pass

Listen to every file at a comfortable volume. Check:
- correct filename and format,
- no unintended silence at the beginning,
- no unwanted click at the end,
- no accidental clipping,
- sensible length,
- consistent volume within a group,
- no duplicate or unused exports.

Then test in Godot with music, UI, and effects playing together. A sound that works alone may disappear inside a busy mix.

## 5. Mini-mission

Create a README for your sound pack with an inventory table:

| File | Purpose | Creator/source | Licence / attribution |
|---|---|---|---|
| `coin_pickup.wav` | Collectible feedback | Your name or source | State the actual terms |
| `player_jump.wav` | Jump feedback | Your name or source | State the actual terms |

Replace the sample rows with the real assets you use.

## 6. Boss challenge

Hand your audio folder to a developer who did not make it. Ask whether they can identify which sound to use for each event and understand the licence notes without asking you questions.

## Checkpoint

1. Why record the licence for each source?
2. Why test effects in the full game mix?
3. What should an audio README explain?
4. Why is permission important for voice recordings?

<details><summary>Answer key</summary>

1. Asset licences and attribution terms may differ.
2. Other sounds can mask effects or make them too loud.
3. Purpose, filenames, sources, licence, and required attribution.
4. The person should know and agree to how their recording will be used.
</details>
