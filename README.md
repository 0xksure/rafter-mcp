# Rafter — shared memory, skills and agents for your team

[Rafter](https://heyrafter.xyz) is a hosted [MCP](https://modelcontextprotocol.io) server that gives your whole team one shared brain across the AI tools you already use. Capture how your team actually solves tasks — as **memories**, **skills** and **agents** — and every teammate's Claude, Cursor or ChatGPT session starts with that context instead of a blank slate.

```
https://app.heyrafter.xyz/api/mcp
```

Remote server, Streamable HTTP transport, OAuth 2.1 sign-in (browser flow, dynamic client registration — no API keys to paste).

## Connect

**Claude Code**

```sh
claude mcp add --transport http rafter https://app.heyrafter.xyz/api/mcp
```

**Claude Desktop / claude.ai** — Settings → Connectors → *Add custom connector* → paste `https://app.heyrafter.xyz/api/mcp`.

**Cursor** — add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "rafter": { "url": "https://app.heyrafter.xyz/api/mcp" }
  }
}
```

**ChatGPT** — Settings → Connectors → enable *Developer mode* → *Create* a connector with the same URL.

**Anything else that speaks MCP** — point it at the URL above; the server handles the OAuth dance.

First connection opens a browser sign-in (Google, GitHub or email) and a consent screen scoped to one of your workspaces.

## Tools

| Tool | What it does |
| --- | --- |
| `search` | Full-text + entity search across your workspace's memories, skills and agents |
| `fetch` | Fetch one artifact with its graph edges (`cites`, `cited_by`, `links`) to follow |
| `add_memory` | Write a durable team learning back from any session |
| `upsert_artifact` | Create or update a skill / agent / memory (versioned) |
| `get_artifact` / `list_artifacts` / `delete_artifact` | Read, browse and remove artifacts |
| `create_workspace` / `create_team` | Set up shared spaces |
| `invite_users` / `list_members` / `set_member` | Bring the team in, manage roles |
| `whoami` | Current user + workspace context |

Artifacts are versioned, and `[[wiki links]]` between them resolve into a real graph — so `fetch` returns not just the document but what it cites and what cites it.

## What teams use it for

- **Stop repeating yourself**: decisions, conventions and gotchas written once, recalled in every teammate's session.
- **Turn one person's workflow into everyone's skill**: capture the steps that worked, run them from any MCP client.
- **Onboarding**: new teammate connects, asks "how do we do X here", gets the team's actual answer.

## Install the Rafter skill

Two ready-to-use files make your AI actually *use* the shared brain instead of guessing:

- [`skill/SKILL.md`](skill/SKILL.md) — a Claude Code skill: drop it into `.claude/skills/rafter/SKILL.md` in your project (or `~/.claude/skills/rafter/`) and your agent searches Rafter before answering "how do we do this" questions, and writes learnings back.
- [`examples/startup-prompt.md`](examples/startup-prompt.md) — a startup prompt to paste into any tool's project/system instructions for the same behavior without skill support.

## Links

- Site: [heyrafter.xyz](https://heyrafter.xyz)
- Pricing: [heyrafter.xyz/pricing](https://heyrafter.xyz/pricing/)
- Privacy: [heyrafter.xyz/privacy](https://heyrafter.xyz/privacy/)

The hosted server itself is closed-source; this repository is its public home — docs, connect snippets, and the place to [open an issue](https://github.com/0xksure/rafter-mcp/issues).
