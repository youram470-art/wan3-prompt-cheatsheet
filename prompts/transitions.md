# Transitions

Seven templates for the joins between shots. A transition prompt has to describe both halves of
the join; if it only describes the middle, the model produces a morph that looks like a mistake.

---

### 24 · Match cut on shape

```
Shot A: a round {object_a} seen face-on, filling the frame, {light_a}. Camera holds. Shot B: the
same circular composition, now {object_b}, matched in size and position at the centre of frame,
{light_b}. The cut happens at the point where both circles are identical, 1 second of overlap,
24 fps.
```

**Slots** — `{object_a}` a wall clock · `{object_b}` a manhole cover · `{light_a}` flat daylight
**Use when** you want the cut to be felt rather than seen.

---

### 25 · Whip pan

```
Whip pan left across {place}, horizontal motion blur streaking the frame for 6 frames, ending on
{subject} standing still in sharp focus, camera settles without overshoot, 35mm, f/2.8, 24 fps.
```

**Slots** — `{place}` a kitchen · `{subject}` a woman in an apron
**Use when** the next shot needs energy rather than a clean cut.

---

### 26 · Foreground wipe

```
Camera tracks right, a {foreground_object} passes within centimetres of the lens and fills the
frame for four frames, then clears to reveal {place}, 28mm, f/4, shallow foreground blur, constant
speed, 24 fps.
```

**Slots** — `{foreground_object}` a pillar / a passing bus · `{place}` a station platform
**Use when** the transition has to hide a location change.

---

### 27 · Light change dissolve

```
Static shot of {place} lit by {light_a}, exposure held constant while the practical lights fade
out and {light_b} comes up over two seconds, the physical scene unchanged, 24mm, f/5.6, 24 fps.
```

**Slots** — `{light_a}` warm afternoon sun · `{light_b}` cold blue night
**Use when** time passes inside one location.

---

### 28 · Element morph, locked camera

```
Locked-off shot of {element} on a plain surface, the material transforming from {state_a} to
{state_b} in place, edges staying fixed to the frame, no camera movement, 50mm, f/8, even
lighting so the change is the only event, 24 fps.
```

**Slots** — `{element}` a pile of sand · `{state_a}` dry grains · `{state_b}` wet glass beads
**Use when** a graphic or title needs to arrive without a cut.

---

### 29 · Push through a doorway

```
Camera pushes forward at constant speed through {opening}, passing from {place_a} into {place_b},
focus staying at 3 metres through the move, 24mm, f/4, single continuous take, no cut, 24 fps.
```

**Slots** — `{opening}` a half-open door · `{place_a}` a hallway · `{place_b}` a lit studio
**Use when** the video moves between chapters.

---

### 30 · Speed ramp on action

```
Shot of {subject} {action}, captured at 120 fps, playback ramping from real time down to quarter
speed at the moment of impact, motion blur consistent with the ramp, 50mm, f/2.8, 24 fps output.
```

**Slots** — `{subject}` a dancer · `{action}` landing a jump
**Use when** the cut point is an action peak, not a visual one.

---

**Tip** — render both sides of a transition at the same duration and resolution. A 3-second shot
cut against a 5-second shot will not line up when the model is asked to generate the join.
