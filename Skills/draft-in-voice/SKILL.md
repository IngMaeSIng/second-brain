---
name: draft-in-voice
description: Draft a post, landing-page section, email, or any piece of copy that sounds like this project — by reading the project's own brand voice and marketing notes from the vault first, instead of defaulting to a generic LLM voice. Trigger when the user asks to write, draft, or rework copy for the project. Triggers — "draft a post", "write copy for", "write this in our voice", "make it sound like us", "rework this in our tone", "write a launch post", "draft the landing copy".
---

# Draft in Voice — write like this project

This skill drafts copy grounded in the project's *own* documented voice, not a generic one. The difference is reading the brand and marketing context from the vault before writing a single line.

## Mandatory setup

1. Call `list_allowed_directories`; find the vault root (folder with `00. Vault Rules & Guide.md`).
2. Read the voice and tone notes in `06. Brand/` (e.g. a "Brand voice" note). This is the source of truth for how the project sounds — including any banned words or phrases it lists.
3. Read the relevant context in `10. Marketing/` (positioning, channels) and `07. Product/` (positioning) for what the project is and who it's for.
4. Read the style section of `00. Vault Rules & Guide.md`.

If `06. Brand/` has no voice note yet, say so and ask the user for two or three lines on how the project should sound before drafting — don't guess.

## Process

1. **Ground in context** — pull the voice principles, the positioning, and the target audience from the notes above. Note any banned words.
2. **Check what already exists** — search the vault for prior notes on the topic (hand off to `vault-keeper` Recall if useful) so the draft builds on, not repeats, existing thinking.
3. **Draft** — one idea per piece. Open with a concrete, specific image, not a thesis. Match the channel (a post is short; a landing section is scannable; an email is direct).
4. **Self-check** against the voice note: does it use the banned words? Does it sound like the project, or like a generic model? Does it lean on something only this project can say (a real number, a real decision, a real story from the vault)?
5. **Place it** — save to `10. Marketing/` (or `10. Marketing/Posts/` for published pieces) only when the user asks, using the Post template. Until then the draft lives in chat.

## Rules

- Write from the documented voice, not a generic one. If the voice note bans a word, never use it.
- One idea per piece. Cut the intro down to the line the thought can't stand without.
- Don't invent product facts, numbers, or features the vault doesn't contain. If you need a fact that isn't there, ask.
- The user writes the final call. Draft, mark your reasoning where it helps, let them decide.
- Don't flatter the project or rubbish competitors.
