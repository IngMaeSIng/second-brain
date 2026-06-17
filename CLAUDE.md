# Working in this vault

This is a structured second brain for one project. It holds durable knowledge in plain Markdown. You can read and write it. Follow the rules below so your output lands where the human expects it and matches the rest of the vault. The full version for humans is `00. Vault Rules & Guide.md` — this is your condensed copy.

## What you're for

- **Status:** "What's done, and what's left before the next milestone?"
- **Context research:** "Show me everything we know on X, and flag the gaps."
- **Backlog:** "Here's a new idea — is something like it already here? If not, add it."
- **Drafting in our voice:** "Using the brand voice and marketing notes, draft a post that sounds like us."
- **Deep research:** "Start from what we already know so we don't research the same thing twice."

Work from the vault's own context. Don't invent facts the vault doesn't contain — if it's not here and not given, say so.

## Where things live (routing table)

| Task / content | Read or write in |
|---|---|
| Vision, roadmap, north-star, OKRs | `02. Strategy/` (goals in `Strategy/Goals/`) |
| A person (team, advisor, candidate, partner) | `03. Team/` |
| Pricing, finance, legal, partnerships | `04. Business/` |
| Launch plan or retro | `05. Releases/` |
| Voice, identity, logo, palette, type | `06. Brand/` |
| Positioning, feature spec, product mechanics (what/why) | `07. Product/` |
| Design system, components, UX flows | `08. Design/` |
| Architecture, integrations, tech decisions (how) | `09. Engineering/` |
| Channels, campaign copy, published posts | `10. Marketing/` |
| A cross-functional decision with rationale | `11. Decisions/` |
| Research, interviews, PMF, RAT | `12. Research/` |
| A competitor, partner org, vendor | `13. Companies/` |
| A meeting note | `14. Meetings/` |
| Support procedures, FAQ, refunds | `15. Customer Ops/` |
| Anything you can't place yet | `01. Inbox/` |

Routing edge cases: Brand = applies everywhere; Design = product-specific. Product = what/why; Engineering = how. Marketing research goes in Research (tagged `domain/marketing`). People → Team; organizations → Companies.

## Conventions you must follow

- **One concept, one note.** Reference with `[[wikilinks]]`; never duplicate a file.
- **Use the templates** in `16. Meta/Templates/` (Note, Decision, Meeting, Person, Release, Post). Fill the frontmatter.
- **Tag every note** with at least its `domain/X`. Domain axis is a closed list: `team, business, brand, product, design, engineering, marketing, research, customer-ops`.
- **Naming:** `Title Case.md`. Meetings and decisions get an ISO date in front (`2026-06-17 — ...`).
- **Indexes** are named with their folder number (`07. Product Index.md`) and sort first. Don't break the Dataview blocks inside them.
- **Two folder levels max.**
- **Link up:** set `root:` in a new note's frontmatter to its domain index.
- When a new decision replaces an old one, set the old to `status: superseded` and add `superseded-by`.

## Before you write

Check whether a note on the topic already exists (search the relevant folder's index first — it's cheaper than scanning every file). If it exists, update it. If not, create it from the right template, in the right folder, with frontmatter and tags filled.
