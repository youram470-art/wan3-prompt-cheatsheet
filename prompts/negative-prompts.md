# Negative prompts

What to exclude, and why. Most text-to-video models accept a negative field; use it for faults
that are consistent, not for faults you have seen once.

## Always worth excluding

| Exclude | Why it shows up |
| --- | --- |
| `text, watermark, caption, logo, signature` | models trained on captioned footage reproduce the caption |
| `extra fingers, extra limbs, fused hands` | hands are the highest-error region in any render |
| `warped face, distorted features, double face` | identity drifts fastest in the first and last second |
| `flicker, exposure pumping` | per-frame exposure is estimated, not measured |
| `jitter, warping background, melting edges` | long lenses and shallow focus amplify it |
| `cartoon, illustration, 3d render, cgi` | only if you want photographic output |
| `slow motion` | only if you asked for real time — otherwise the model defaults to it |

## Conditional

| Exclude | When |
| --- | --- |
| `letterbox, black bars` | when the frame has to be full |
| `shallow depth of field, bokeh` | when everything must be readable (product wide shots) |
| `grain, noise` | when the output is going into a clean digital edit |
| `crowd, people in background` | when the location has to read as empty |
| `reflections, glass glare` | when the product surface must stay readable |

## What not to put in a negative prompt

- **Style words you also used positively.** `cinematic` in the prompt and `flat lighting` in the
  negative will fight; the render usually splits the difference and looks soft.
- **Long lists.** Past roughly 15 tokens the negative prompt starts dropping terms on most
  models. Split into two passes instead.
- **Anything you have not seen fail.** A negative term you never needed costs you a term you did.

## A workable default

```
text, watermark, logo, signature, extra fingers, fused hands, warped face, double face,
flicker, exposure pumping, jitter, warping background, melting edges
```

Start there, then remove entries as your prompt gets more specific. A short prompt with a long
negative list is usually a prompt that has not decided what it wants.
