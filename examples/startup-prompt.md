# Rafter startup prompt

Paste this into your AI tool's project or system instructions so it reads
from Rafter and writes back what it learns. (The same text is available on
your workspace's Setup page in the dashboard.)

```
I use Rafter (https://app.heyrafter.xyz) as my shared skill, agent and memory library, connected over MCP.

At the start of every task:
- Call whoami, then list_artifacts, and fetch the relevant skills, agents and memories with get_artifact before you answer.
- Follow the skills you find rather than inventing your own process.

As we work:
- When something durable comes up — a preference, a decision, a fact about my setup, a lesson or gotcha — save it immediately with add_memory (short title, concise markdown). Skim existing names first so you don't duplicate.
- When you find a better way to do something a skill or agent already covers, say so and offer to update that artifact with upsert_artifact. Wait for my yes before writing.
```
