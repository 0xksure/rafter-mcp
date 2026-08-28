---
name: rafter
description: Search and reuse this team's skills, agents and memories from Rafter; use when answering how-do-we/what-did-we-decide questions
---

# Rafter

Rafter holds this team's shared skills, agents and memories, connected
over MCP at https://app.heyrafter.xyz/api/mcp.

Use it whenever a question is really "how do we do this" or "what did we
decide" -- team process, conventions, prior decisions, a gotcha someone on
the team already hit.

## How to use it

1. Call `search` first, before answering a team-process question from
   memory or guessing.
2. `fetch` the top results and read them. Follow relevant edges
   (`cites`, `links`, `cited_by`) with further `fetch` calls when
   they matter.
3. Prefer current versions.
4. Write durable learnings back right away with `add_memory` (short
   title, concise markdown) -- skim existing names first so you don't
   duplicate one.
5. Never invent team process that a Rafter search could have answered.
