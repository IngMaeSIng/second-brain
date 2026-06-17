# Skills

Claude skills that operate this vault. Point your agent's skills directory at this folder, or copy the skill folders into it (e.g. `~/.claude/skills/`) — see your agent's docs for where skills live. Each skill reads `00. Vault Rules & Guide.md` and `CLAUDE.md` at runtime, so its behavior stays grounded in your vault's actual rules.

- **vault-keeper** — operate the vault: recall ("what do we know about X?"), promote a draft from Inbox into the right domain folder, find related notes, assess topic coverage.
- **draft-in-voice** — draft copy that sounds like the project, by reading its brand voice and marketing notes from the vault first.

Both need a Filesystem MCP server pointed at the vault so the agent can read and write notes.
