# Second Brain — a project vault for you and your AI agent

A ready-made [Obsidian](https://obsidian.md) structure that turns your notes into a second brain an AI agent can read and write. Download it, open it as a vault, fill it with your project — and your agent works from your context instead of guessing.

Built by [Paul Sikorsky](https://sikorsky.design). The thinking behind it: [sikorsky.design/second-brain](https://sikorsky.design/second-brain/).

## Why

Models got good. The bottleneck now isn't the model — it's how much context it has about you and your work. Without context, an agent reaches for an average answer off the internet, or invents one. A structured vault in plain text closes that gap: the context lives in files, the agent reads them, nothing gets distorted or lost.

You already design structure for other people's products every day — information architecture, naming, hierarchy. This is the same skill, turned on your own work. And you don't need to code for it.

## Who it's for

Founders, indie makers, designers, and product people who run a project and want an agent that actually knows it. This is the **project / product** template. (A personal-life version is a separate thing — don't mix the two.)

## What's inside

```
00. Dashboard               your daily entry point
00. Vault Rules & Guide     how the vault works, for you and the agent
CLAUDE.md                   the agent's condensed rules + routing table

01. Inbox/                  fast capture
02. Strategy/ (Goals/)      vision, roadmap, north-star, OKRs
03. Team/ (Operations/)     people, cadence, tool stack, hiring
04. Business/               pricing, finance, legal, partnerships
05. Releases/               launch plans and retros
06. Brand/                  voice, identity, logo, type
07. Product/                positioning, specs, mechanics
08. Design/                 design system, UX, components
09. Engineering/            architecture, integrations, tech decisions
10. Marketing/              channels, copy, campaigns
11. Decisions/              ADRs with rationale
12. Research/               PMF, RAT, interviews, synthesis
13. Companies/              competitors, partners, vendors
14. Meetings/               syncs, ad-hoc, interviews
15. Customer Ops/           support procedures, FAQ, refunds
16. Meta/                   templates, attachments, bases
17. Archive/
```

Every domain folder ships with an **index note** that doubles as documentation — it tells you (and the agent) what belongs there. Six note templates (Note, Decision, Meeting, Person, Release, Post) live in `16. Meta/Templates/`.

## Install (no terminal)

1. **Download** this repo as a ZIP (green *Code* button → *Download ZIP*) and unzip it. Rename the folder to your project if you like.
2. **Open** Obsidian → *Open folder as vault* → select the folder.
3. **Enable plugins.** Turn on the built-in **Templates** core plugin (Settings → Core plugins) and set its template folder to `16. Meta/Templates`. Install the **Dataview** community plugin (Settings → Community plugins) — the indexes need it. Add **Obsidian Git** too if you'll sync via GitHub.
4. **Pin** `00. Dashboard` and `00. Vault Rules & Guide`. Read the Rules once.

Prefer Git? `git clone` the repo and open it as a vault instead — same result, with version history.

## Requirements

- **Obsidian** (free).
- **Dataview** (community plugin) — required. The indexes are live Dataview queries; without it they render as plain code blocks.
- **Templates** (core plugin, built in) — for the note templates. Enable it and point it at `16. Meta/Templates`.
- **Obsidian Git** (community plugin) — optional, for GitHub sync.

## Connect your agent

The vault is plain text, so any agent with filesystem access can use it.

- Drop a Filesystem MCP server pointed at this folder into your agent (e.g. Claude Desktop), so it can read and write the notes.
- The agent reads **`CLAUDE.md`** at the root — its rules and routing table. Keep it in sync with the human Rules.
- Two skills ship in **`Skills/`** — `vault-keeper` (recall, promote, link, gap-check) and `draft-in-voice` (write copy that sounds like the project). Point your agent's skills directory at them. See `Skills/README.md`.

Full walkthrough: [sikorsky.design/second-brain](https://sikorsky.design/second-brain/).

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — use it freely, including commercially, adapt it however you like; just credit Paul Sikorsky and link back. See `LICENSE`.

---

Made by Paul Sikorsky while building **[Baselife](https://baselife.me)** — a journal and life calendar for living with more intention. More on life design, mindful productivity, and building in public: [t.me/initsrightplace](https://t.me/initsrightplace).
