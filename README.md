# micron-sketch
Turn a real photo — buildings and streets especially — into a ready-to-paste
image-generation prompt for a hand-drawn micron-pen architectural sketch:
loose black ink linework, cross-hatching, a small human figure for scale, and
exactly one color accent.
This is a Codex / Antigravity-style agent skill, not a standalone app. It doesn't
generate images itself — it analyzes your reference photo and writes a
detailed prompt you paste into an image-gen tool (Midjourney, DALL-E, Nano
Banana, etc.).
Structure
```
.
├── README.md
├── examples/
│   ├── images/          — source reference photo(s) used for calibration
│   └── prompts.md       — example generated prompts
└── micron-sketch/
    ├── SKILL.md
    ├── assets/examples/
    └── references/
        ├── style-dna.md
        ├── scale-figure.md
        ├── composition-patterns.md
        ├── prompt-template.md
        └── qa-checklist.md
```

Notes
One fixed style, applied faithfully to whatever building/street is in the
source photo — see `references/style-dna.md` for what's fixed and
`references/composition-patterns.md` for how framing adapts per photo.
Example images in `examples/images/` and `assets/examples/` are for style
calibration only, not composition templates to copy.
