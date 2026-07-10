# 🤝 PM CoPartner

> **An open-source collection of AI subagents built for Product Managers.**
> Each agent handles one core PM workflow — from user research to release notes — so you can spend less time on documents and more time on decisions.

---

## What Is PM CoPartner?

PM CoPartner is a set of **5 Claude-powered AI subagents**, each designed around a real PM workflow. You copy a prompt, connect your tools, and the agent does the heavy lifting.

No specific toolstack required. Every agent lists a **primary path** (e.g. Notion + Linear) and a **fallback path** (plain files, Google Docs, email) — so it works whether you're at a seed-stage startup or a scaled org.

---

## The 5 Agents

| # | Agent | What It Does | Run When |
|---|-------|-------------|----------|
| [01](./01-discovery/) | **Insight** | Turns raw user interview notes into a structured insight report | Per research sprint |
| [02](./02-planning/) | **Prioritize** | Scores and ranks backlog items against strategy & OKRs | Weekly |
| [03](./03-specs/) | **Blueprint** | Auto-drafts PRDs from feature requests | Always on / on demand |
| [04](./04-analytics/) | **Pulse** | Compares metrics to targets and sends a digest | Weekly |
| [05](./05-launch/) | **Ship** | Writes user-facing release notes from sprint output | Per release |

---

## How to Use

### Option A — Claude Desktop (Recommended)
1. Install [Claude Desktop](https://claude.ai/download)
2. Open the agent folder you want (e.g. `01-discovery/`)
3. Read `setup.md` to connect any tools you use
4. Copy the prompt from `prompt.md`
5. Paste it into Claude, fill in the `[bracket]` placeholders, and run

### Option B — Claude.ai (No setup)
1. Open [claude.ai](https://claude.ai)
2. Copy the prompt from any `prompt.md`
3. Paste your raw data (notes, tickets, metrics) directly into the chat
4. Fill in the `[bracket]` placeholders and send

### Option C — Scheduled / Automated
1. Use Claude's `/schedule` command (Cowork mode) or a cron + API script
2. Connect MCP integrations listed in `setup.md`
3. Set the run frequency shown in the agent's README

---

## Toolstack Flexibility

Each agent is designed to work with **whatever tools you have**. You don't need Jira, Notion, or Linear.

| If you have... | Use... |
|----------------|--------|
| Notion | Native Notion MCP connector |
| Linear / Jira | Linear or Jira MCP connector |
| Google Drive | Drive MCP connector |
| Just files | Paste content directly into Claude |
| Just email | Forward threads to Claude or paste inline |
| Spreadsheets | Paste CSV rows or attach the file |

Every `setup.md` explains the **minimal path** (no integrations) and the **connected path** (full MCP setup).

---

## Project Structure

```
pm-copartner/
├── README.md               ← You are here
├── CONTRIBUTING.md         ← How to contribute new agents or improvements
├── 01-discovery/
│   ├── README.md           ← What the agent does, when to use it
│   ├── prompt.md           ← The Claude prompt (copy this)
│   └── setup.md            ← Tool connections & fallbacks
├── 02-planning/
│   ├── README.md
│   ├── prompt.md
│   └── setup.md
├── 03-specs/
│   ├── README.md
│   ├── prompt.md
│   └── setup.md
├── 04-analytics/
│   ├── README.md
│   ├── prompt.md
│   └── setup.md
└── 05-launch/
    ├── README.md
    ├── prompt.md
    └── setup.md
```

---

## Who Is This For?

- Solo PMs at early-stage startups with no tooling budget
- Senior PMs at scaled companies drowning in process overhead
- Product teams wanting to standardise how research, specs, and comms are produced
- Anyone who has ever spent a Sunday writing release notes

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

Ideas for new agents, better prompts, or tool-specific setup guides are all fair game.

---

## License

MIT — use it, fork it, improve it, share it.
