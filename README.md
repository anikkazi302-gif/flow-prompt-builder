# Flow Prompt Builder 🎬🐉

Build a **complete Google Flow video prompt** for your AI movie — with the locked camera rule, face lock, second-by-second timing and dialogue attribution.

Fill in the scene, press **Build my prompt**, copy the finished prompt into Flow. Everything runs **in your browser**. No account, no server, no build step, no paid API. It works offline, and nothing you type is uploaded anywhere.

## What the finished prompt contains

Every prompt the tool builds contains all of these, in this order:

1. **Scene header** — scene title, setting, time of day, model, duration and `16:9 widescreen`.
2. **Characters present** — every visible character in full, from their own reference sheet: face, marks, hair, facial hair, build and exact clothes — plus what that character does in this scene. A character who is not ticked gets **no** description and **no** reference photo.
3. **CAMERA RULE** — the locked camera block, verbatim, in every prompt:

   > CAMERA RULE: The camera does whatever it needs to do to show the characters well — it may turn, move, change angle or cut whenever the scene needs it; that is the camera's own job. All camera decisions belong to the camera alone: where to zoom in, where to zoom out, which angle to use, where to use a tracking shot, when to pull back, when to push forward, who to focus on, and when to zoom onto a face — whatever makes the scene beautiful and brings out its emotion, pain, anger and feeling. The characters pay NO attention to the camera at all: they NEVER look at it, NEVER act for it, and do nothing for it — they stay in their own business and live their scene naturally, as if no camera were there.

4. **FACE LOCK** — verbatim, in every prompt:

   > Faces must match the reference photos exactly — not even slightly.

5. **TIMING** — a second-by-second breakdown covering the **whole** duration with no second skipped (0s to the final second).
6. **DIALOGUE** — every spoken line labelled with its speaker, and every gap written out explicitly (`— short gap —` / `— long gap —`). Each character speaks ONLY their own lines.
7. **STANDING RULES** — always included:
   - NO blood ever — injury may be shown, never blood.
   - 16:9 widescreen.
   - One continuous shot — no cuts.
   - Every character speaks ONLY their own lines; one person's line is NEVER spoken by another.
   - Movements are completely natural and very fast.
   - Every needed sound is present properly at its moment — none missing, none faint.
   - No character is dropped, no character is changed, no face is changed.

## The characters

The tool carries full descriptions for 7 characters, taken from their locked reference sheets:

| Character | Description (short version — the prompt carries the full text) |
|-----------|----------------------------------------------------------------|
| **Priya** | Young woman, long dark hair, soft gentle face, simple old worn dress. She NEVER smiles. |
| **Ember** | Pure white dragon, smooth fine white scales (slightly glossy, never large rough plates), dark reddish-brown eyes with a dark vertical pupil. ALWAYS pure white. |
| **Father Victor** | Older priest, dark wavy hair, grey-flecked beard, long black hooded clerical cloak, light stole, cross pendant. |
| **Liza** | Heavier woman, middle-parted black hair in a low bun, round full weathered face, deep-set dark-brown eyes, old worn long black dress, old worn black crocheted fringed shawl, worn black flat shoes. ALWAYS black, ALWAYS old and worn. |
| **Martha** | Older woman, grey hair tied back, lined weathered face, old worn shawl over a long plain dress. |
| **Raju** | Young MAN, grown adult aged 25–27 (NOT a child, NOT a teenager); lean and slim; round full face, warm brown skin, thick black brows, brown eyes, broad nose, small dark mole under his RIGHT eye, black mustache and short full boxed beard, thick wavy voluminous black hair swept up and back; beige cream lace-up linen shirt, dark loose trousers, brown leather boots. |
| **Bram** | Heavy-set man, short dark hair, short beard, light shirt with rolled sleeves, brown vest, stained work apron. |

## The models

| Model | When to use it |
|-------|---------------|
| **Veo 3.1 Fast** | Dialogue, close-ups, emotional scenes and fast action. (Default.) |
| **Veo 3.1 Light** | Simple wide or static shots with little movement. |
| **Omni Flash** | Tests and drafts (720p workflow). Use for trying a scene before the final take. |

## How to use it — step by step

### Step 1 — Scene basics

1. **Scene title** — a short name for the clip, e.g. `Ember steps out of the cottage`. If you leave it empty, the prompt says "Untitled scene".
2. **Setting** — where the scene happens, e.g. `in front of Priya's old stone cottage`. If empty, it defaults to "An old village setting".
3. **Time of day** — pick from the list: Morning / Daytime (both overcast grey sky, no sun), Evening (dim, fading light), Night (dark, cold, moonlight only), Dawn (pale first light).
4. **Duration (seconds)** — how long the clip is. Minimum 5, maximum 30. Default is 10.

### Step 2 — Characters in this scene

1. **Tick** every character who is visibly seen in the scene. Unticked characters are left out completely — no description, no reference photo.
2. When you tick a character, an **action box** appears under their description. Write what that character does in this scene, e.g. for Ember: `lowers its head toward Priya, mouth closed, throat glowing red`.
   - If you leave the action box empty, the tool uses that character's default action (shown as the grey placeholder text in the box).

### Step 3 — Dialogue

1. The form starts with two rows: one filled in as an example (`Priya: "Ember, don't hurt anyone."` — short gap) and one empty row.
2. For each spoken line, in order:
   - **Speaker** — pick from the dropdown. It lists the characters you ticked in Step 2, plus `Crowd (shouting together)` and `Off-screen voice`.
   - **Line** — the exact words, e.g. `Priya can control the monster!`
   - **Gap** — what follows the line: `No gap`, `Short gap` or `Long gap`. The gap is written out in the prompt as `— short gap —` or `— long gap —`.
3. Press **＋ Add a dialogue line** to add another row. Press **✕** on a row to remove it.
4. Rows with no speaker or an empty line are ignored when building.
5. If the scene has no dialogue at all, delete all rows (or leave them empty) — the prompt will say "No dialogue in this clip — the scene plays in silence, with only natural sound."

### Step 4 — Model

Pick one of the three models (see the table above). Veo 3.1 Fast is selected by default.

### Step 5 — Build and copy

1. Press **🎬 Build my prompt**.
   - If no character is ticked, a red message tells you to tick at least one character — the prompt is not built until you do.
2. The finished prompt appears in the dark box. Read it through: check the timing covers your full duration, every line has the right speaker, and every gap is written out.
3. Press **📋 Copy prompt**. The button briefly turns green and says "✅ Copied!". Paste it into Google Flow.
4. **Clear form** wipes the whole form (title, setting, duration back to 10, all characters unticked, dialogue back to one empty row) so you can start the next clip.

### How the timing is built

The tool divides your duration into segments that always cover the full clip with no second skipped:

- **Opening** — 2 seconds: the scene opens, setting established, every character in place.
- **Each dialogue line** — 2 seconds: the speaker says the line.
- **Each gap** — short gap 1 second, long gap 2 seconds: no dialogue, characters hold their positions.
- **Final action** — the rest of the duration: the characters' actions from Step 2 play out until the last frame.

If your dialogue is long for the duration you picked, the segments are shortened proportionally (never below 1 second each) so the breakdown still covers exactly 0 seconds to your full duration.

## How to run it

There is nothing to install and nothing to build.

- **Double-click `index.html`** — it opens in your browser and works.
- **Or serve it:** `python3 -m http.server` in this folder, then open `http://localhost:8000`.
- **Or host it:** copy this folder to any static host (GitHub Pages, Netlify, Vercel). It is one HTML file; no backend is needed.
- It works **offline** — there are no external scripts, fonts, or images. All styling is plain CSS in the file.

## File list

```
flow-prompt-builder/
├── index.html   — the whole app: page, styling, character data, locked text blocks, prompt builder logic
├── README.md    — this file
└── LICENSE      — MIT License
```

## How to contribute

Contributions are welcome — new characters, new models, better timing, new features. The flow is the standard GitHub flow:

1. **Fork** this repository (the Fork button, top right on GitHub).
2. **Clone** your fork to your computer: `git clone https://github.com/YOUR-USERNAME/flow-prompt-builder.git`
3. **Create a branch** for your change: `git checkout -b add-new-character`
4. **Make your change** in `index.html` (everything lives in that one file) and test it by opening the file in a browser — build at least one prompt with your change and read the whole output before submitting.
5. **Commit** with a clear message: `git commit -m "Add Martha's full description"`
6. **Push** to your fork: `git push origin add-new-character`
7. **Open a Pull Request** on GitHub, describing what you changed and why.

### Adding a new character

Add one object to the `CHARACTERS` array in `index.html`. Every field is required — no field may be left empty:

```js
{
  id: "tomas",                       // short, lowercase, no spaces — used internally
  name: "Tomas",                     // shown in the checkbox list and speaker dropdown
  desc: "Tomas — ...",               // FULL description: face, marks, hair, facial hair,
                                     // build, exact clothes from head to feet
  defaultAction: "stands at the market stall, watching"  // used when the action box is empty
}
```

Rules for new characters: the description must come from that character's own reference photo or sheet — face features, identifying marks, hair, facial hair, build, exact clothes — written so completely that the character is unmistakable even in a wide shot. Never write "boy" or "girl" for an adult character. Never change an existing character's description without the reference sheet to back it.

### Adding a new model

Add one object to the `MODELS` array in `index.html`:

```js
{ id: "fast2", name: "Veo 3.1 Fast 2", hint: "When to use it, in one sentence." }
```

### Changing the locked text

The `CAMERA_RULE` and `FACE_LOCK` constants at the top of the script are the locked blocks that go into every prompt verbatim. Do not edit them unless the project's locked rules themselves change — and if they do, say so in your Pull Request.

### Reporting a bug

Open an Issue on GitHub: say which browser you used, what you filled in, and what the built prompt got wrong (paste the broken part of the prompt).

## License

MIT License — see [LICENSE](LICENSE). Free to use, copy, modify and share.
