# Prompt Cheatsheet for Text-to-Video Models

30 reusable prompt templates for short AI video shots, grouped by the kind of shot you need:
faces, landscapes and camera movement, product beauty shots, and transitions.

Each template is a filled-in skeleton: the shot description is already written, and only the
bracketed `{slots}` change between projects. Copy one, fill the slots, render.

## Why a template instead of a prompt

A prompt that "works" is usually a prompt that names the camera, the light and the motion
separately. If you leave one out, the model invents it, and the invented part is what makes a
shot look generated. The templates below always spell out:

- **subject + action** — what is in frame and what it is doing
- **framing** — shot size, lens, depth of field
- **light** — direction, quality, colour temperature
- **motion** — camera movement *and* subject movement, at the pace you want
- **texture** — grain, film stock, or a clean digital look

## Contents

| File | Templates | Shots |
| --- | --- | --- |
| [`prompts/character-closeups.md`](prompts/character-closeups.md) | 8 | faces, hands, emotional beats |
| [`prompts/landscape-camera-moves.md`](prompts/landscape-camera-moves.md) | 8 | establishing shots, moves, aerials |
| [`prompts/product-showcase.md`](prompts/product-showcase.md) | 7 | packshots, macro, tabletop |
| [`prompts/transitions.md`](prompts/transitions.md) | 7 | match cuts, wipes, morphs |
| [`prompts/negative-prompts.md`](prompts/negative-prompts.md) | — | what to exclude, and why |

## How to use a template

1. Pick the shot you need from the table above.
2. Replace every `{slot}`. Leave nothing in brackets — models read `{slot}` as literal text.
3. Keep the sentence order. Most text-to-video models weight the beginning of a prompt more
   heavily, so subject and framing go first, texture last.
4. Render at the shortest duration that contains the action, then extend. Long single renders
   drift; two short ones cut together hold up better.
5. Change one variable at a time when iterating. If you change the lens and the light together
   you will not know which one broke the shot.

## Slot conventions

| Slot | Fill with | Example |
| --- | --- | --- |
| `{subject}` | person + age + one identifying detail | `a man in his late 40s, grey stubble` |
| `{place}` | a named location, not a mood | `a tiled laundromat at 11pm` |
| `{mood}` | one adjective | `wary` |
| `{product}` | object + material | `a matte ceramic mug` |
| `{palette}` | 2–3 colours | `teal, bone white, sodium orange` |

## A note on models

The templates are model-agnostic: the structure (subject → framing → light → motion → texture)
is what carries over. They were written and tested against [Wan 3.0](https://wan-3.io/), which
takes the same five-part description in text-to-video and image-to-video mode. The same templates
work in [Pavo AI](https://pavoai.app/), where the cast is defined once and reused across shots.

## Licence

MIT — use them commercially, no attribution required.
