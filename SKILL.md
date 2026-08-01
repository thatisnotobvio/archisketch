---
name: archisketch
Description: Turns a real reference photo (buildings, streets, architecture especially) into a ready-to-paste image-generation prompt for a hand-drawn micron-pen / fineliner architectural sketch — loose black ink linework, cross-hatching, a small human figure for scale, and exactly one color accent. Use whenever the user asks to "sketch this," "turn this photo into a sketch," wants a "micron sketch," "pen and ink drawing," "line art version," or uploads a building/street photo and asks for a hand-drawn illustration of it, even if they don't name the style. Output is a text prompt for an external image-gen tool (Midjourney, DALL-E, Nano Banana, etc.) — this skill does not generate images itself.
---

# Archi Sketch
Not a generic "make this a sketch" filter. The goal is to take one real photo and translate its specific architectural content — the actual massing, materials, and details in front of the camera — into a single fixed hand-drawn style, the way an architect's on-site sketchbook drawing would. The style never changes between requests; only the subject does.

## Core Rule
Faithfulness over decoration. Every prompt must be traceable back to what's actually in the source photo: material split, window/door count and placement, plant type, camera angle. Don't invent generic "nice building" details that aren't there, and don't skip real details that are.

## Read these references first
- `references/style-dna.md` the fixed visual style (medium, line quality, shading technique, color rule). Constant across every output.
- `references/scale-figure.md` rules for the recurring human-figure and foreground-planting elements every sketch includes.
- `references/composition-patterns.md` which framing/angle to choose based on what the photo shows, and the anti-repetition rule.
- `references/prompt-template.md` the exact slot structure the final prompt must follow.
- `references/qa-checklist.md` run this against your draft prompt before presenting it.

Read all of these before drafting a prompt — they're short and the mistakes they prevent (skipping the color-accent rule, forgetting the blank sky, generic massing description) are the most common failure modes.

## Workflow

### 1. Digest the reference photo
First, look at whatever the user provides — a photo, several angles of the same building, a screenshot, or a listing link. Extract the concrete details, not a generic caption:
- What is the massing/shape of the building?
- What material is on each surface, and where does the material split fall?
- Where are the windows and doors, and how many?
- What's actually in the foreground — plants, people, vehicles, a curb?
- What is the camera angle, and which facades are visible?
- Where does the light fall, and which side is in shadow? Prioritize the anchor details that make this specific building recognizable — the real material split, the real window count, the real planting — never average or invented "nice building" description.

### 2. Composition check
If the user gives more than one photo of the same building, or asks "which angle should I sketch," decide the composition first and say so in a sentence or two before building the prompt:
- Corner three-quarter, straight elevation, or close detail crop? (see `references/composition-patterns.md`)
- Which facade carries the shadow hatching? Keep this short — this skill produces one prompt per photo, not a shot list or a multi-image spread.

### 3. Prompt generation
If the user asks to "sketch this," "generate," or similar, don't stop to confirm — assemble the prompt immediately using references/prompt-template.md. Every prompt must include:
- Micron pen / fineliner ink, black on white paper
- Loose hand-drawn linework, cross-hatching for shading
- The specific massing/material description from step 1
- The scale figure and foreground planting (references/scale-figure.md)
- Blank white sky and background
- Exactly one named color accent Prohibited: photorealism, full-color rendering, smooth digital gradients, ruler-perfect vector lines, watermarks, more than one color accent, and any generic description not actually drawn from the photo. Never reuse a past example's composition, material split, or planting for a different building — reinvent the specific description each time from what's actually in front of the camera.

### 4. Inspection and iteration
After drafting, check references/qa-checklist.md. Regenerate or edit before showing the user if any of these show up:
- The scale figure or planting was skipped, or reads as pure decoration
- The description reads generic rather than specific to the photo
- A real material or facade distinction got collapsed into one surface
- Zero or more than one color accent
- Sky/background isn't explicitly stated as blank
- The prompt runs over ~150 words

### 5. Save delivery
If the user is working within the workspace, copy the final diagram to:

```text
assets/
```

Name in order:

```text
01-building-name.png
02-building-name.png
```

Retain the original generated files and do not overwrite existing assets unless the user explicitly requests a replacement.

## If no photo is attached

Ask for one. This skill can't produce a faithful prompt from a description alone — the whole point is translating real, specific visual content.
