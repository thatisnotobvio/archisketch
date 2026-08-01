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

