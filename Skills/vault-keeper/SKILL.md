---
name: vault-keeper
description: Operate this project second-brain vault. Trigger whenever the user asks about their notes, vault, or knowledge base, or wants to act on a specific note. Four modes — Recall ("what do we know about X?"), Promote (move a draft from Inbox into the right domain folder, linked and tagged), Connect (find related notes for a note), Topic Gap (assess coverage before writing). Triggers — "what do we know about", "search the vault", "do we have notes on", "promote this from inbox", "where does this go", "find related notes", "suggest links", "is X covered". Also trigger when the user names a note and wants to link it, move it, search it, or find related notes.
---

# Vault Keeper — project second-brain operator

This skill operates a structured project vault as a Recall + Output knowledge base. It promotes drafts from Inbox into the right domain folder, finds connections between notes, answers "what do we know about X?", and spots topic gaps. It follows the contract in `00. Vault Rules & Guide.md` — it does not invent rules.

## Mandatory setup (every session)

1. Call `list_allowed_directories` to find the vault root — the folder containing `00. Vault Rules & Guide.md`.
2. Read `00. Vault Rules & Guide.md`. It is the authoritative spec for folder roles, routing, frontmatter, tags, and naming. Don't act on memory.
3. Read `CLAUDE.md` for the routing table.

Structure: `01. Inbox/` (raw capture) · numbered domain folders each with an index · `16. Meta/` (templates) · `17. Archive/`. Each domain folder's index describes what belongs there.

## Modes

### 1. Recall — "What do we know about X?"

Synthesize from existing notes. Don't fabricate; don't create files unless asked.

1. Search the vault for the topic (`search_files` for filename match, then read candidates).
2. Look in `01. Inbox/` and the domain folders. Distinguish source by location.
3. Synthesize — each claim traces to a note, referenced as `[[Note name]]`.
4. Structure: **Worked-through** (in a domain folder, with links) · **Raw** (in Inbox, with links) · **Tensions** (if notes disagree, flag both with attribution).
5. End with one line: what's NOT covered.

The synthesis stays in chat. It becomes a file only if asked — then create it in `01. Inbox/` with `status: draft`, frontmatter filled, links to sources.

### 2. Promote — Inbox → domain folder

Move a draft into the right domain folder with all criteria met.

1. Identify the note. If unspecified, ask.
2. Read it (frontmatter + body).
3. Check criteria from the Rules:
   - **Single topic** — if multi-topic, don't promote; propose a split.
   - **Title = topic, not source** — if source-flavored, propose a rename.
   - **`root:` set** — if empty, find the domain index (or a broader note) and propose it.
   - **At least 2 `[[wiki-links]]`** — if fewer, search for related notes and propose 2–5 with rationale.
   - **`domain/X` tag** — set it (closed list: team, business, brand, product, design, engineering, marketing, research, customer-ops).
4. Pick the target folder by routing rules (see Rules §3). If unclear, propose two and ask.
5. After the user confirms: update frontmatter (`updated` → today, `status` → `active`, `root` set), then `move_file` from Inbox to the domain folder.
6. Confirm the new path and show the frontmatter diff.

Never auto-promote. Never delete from Inbox — move only.

### 3. Connect — find related notes

1. Read the target note; identify its key concepts.
2. Search the vault for notes on those concepts.
3. Categorize: **Parent** (for `root:`) · **Siblings** · **Children**.
4. Propose 3–7 links with one-line rationale. Don't auto-edit.
5. On approval, insert links naturally in the body.

### 4. Topic Gap — "Do we have notes on X?"

1. Search across Inbox and domains.
2. Report by location, with `[[links]]` and one-line summaries.
3. List cited sources (from `url:` / source frontmatter).
4. Suggest one next move: use an existing note as-is · expand a draft (offer Promote) · start fresh.

## Hard rules

- Read `00. Vault Rules & Guide.md` first, every session. Don't act on memory.
- Never delete files. Move only. Inbox is permanent.
- Never auto-edit on Promote — confirm first.
- Never modify `00. Vault Rules & Guide.md` or `CLAUDE.md`; the user owns those.
- Don't fabricate. If a topic isn't covered, say so. No fake `[[links]]`.
- Use `[[Note name]]` (shortest unique), not path-based links.
- Preserve unknown frontmatter fields on edit. Bump `updated` only on content change.
- Don't add tags outside the vocabulary in the Rules — propose new ones to the user first.

## Frontmatter operations

Use `edit_file` with surgical old/new replacements. Never overwrite the whole frontmatter block — preserve field order and unknown fields. Do separate edits rather than one combined replacement.

## Common pitfalls

- Promoting a multi-topic note — check single-topic first; nudge a split.
- Inventing a parent — if none exists, ask before creating.
- Path-based links — use shortest unique name.
- Reading 200 files for a broad recall — narrow with filename search first, prefer 5–10 targeted reads.
