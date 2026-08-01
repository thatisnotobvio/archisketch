# QA Checklist

Run this against every draft prompt before showing it to the user. If any item fails, fix the prompt — don't present it and caveat it.
- Names the medium: "micron pen" / "fineliner" and "cross-hatching" or "hatching" both appear.
- Describes the building's actual massing and material split from the source photo — not a generic "nice house" description.
- Mentions the scale figure (pose + location).
- Mentions foreground planting matching what's actually in the photo.
- Mentions the ground plane (pavement/path texture, curb line).
- States the sky/background is left blank white.
- Names exactly one color accent and states everything else is black and white — never zero, never more than one.
- Composition pattern matches the source photo's actual camera angle (see composition-patterns.md) — not defaulted without checking.
- Under ~150 words.
- Includes the negative-prompt line (avoid photorealism, full color, digital gradients, ruler-perfect lines, watermarks, extra accents).
- Presented as a single copy-pasteable code block, not scattered across prose.
- Response doesn't claim or imply an actual image was generated — this skill produces a prompt for the user to run elsewhere.

## When revising an existing prompt
- Re-output the whole prompt, not a diff or "just change X to Y."
- Everything not explicitly asked to change stays the same (composition, unrelated details) — don't regenerate from scratch and drift.
