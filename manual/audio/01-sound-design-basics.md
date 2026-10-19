# 01 — Sound Design Basics

Sound design is the process of choosing or creating audio that helps a player understand what is happening and feel the game's mood.

## Common categories

- **UI sounds:** button clicks, menu open/close, confirmation, error, notification.
- **Gameplay effects:** jump, land, collect, hit, dash, door, switch, ability.
- **Environment:** wind, rain, room tone, water, machinery, forest ambience.
- **Music:** title theme, exploration, action, victory, game over.
- **Feedback sounds:** short audio cues that confirm a meaningful action.

## Design the sound's job first

Before creating a sound, answer:
1. What event causes it?
2. What should the player understand or feel?
3. How long should it last?
4. Will it play often?
5. Must it be heard over music or other effects?

A button pressed many times usually needs a short, quiet sound. A rare event can have a longer cue. Important information should not rely on sound alone; also use visuals, text, animation, or vibration where appropriate.

## Why pixel games often use short electronic sounds

Retro-inspired games may use simple waveforms, quick pitch changes, noise bursts, and short envelopes. These are stylistic choices, not requirements. Pixel art does not mean every game must sound like an old console.

## Useful audio words

- **Pitch:** how high or low a sound seems.
- **Duration:** how long it lasts.
- **Attack:** how quickly the sound starts.
- **Decay:** how quickly it becomes quieter after the initial peak.
- **Sustain:** the level held while a note continues.
- **Release:** how the sound fades after it is triggered to stop.
- **Loop:** a section that repeats.
- **Clipping:** distortion caused by the signal exceeding the available digital level.

## Keep a sound list

Create a simple list before recording or generating files:

| Event | File name idea | Design goal |
|---|---|---|
| Button press | `ui_click.wav` | Short and subtle |
| Collect item | `item_pickup.wav` | Bright, positive cue |
| Jump | `player_jump.wav` | Fast, readable |
| Error | `ui_error.wav` | Clear without being harsh |
| Level complete | `level_complete.wav` | Distinct celebratory cue |

Use descriptive names and keep a consistent naming style. This makes it easier to find sounds when the project grows.
