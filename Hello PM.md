# Hello PM — Quick Reference for PM CoPartner

Everything you need to know in one place. No need to dig through subfolders.

---

## What Is PM CoPartner?

An open-source collection of **5 Claude-powered AI subagents** for Product Managers. Each agent handles one core PM workflow. You copy a prompt, add your data, and Claude does the work.

**Zero hard dependencies.** Every agent works with plain copy-paste. MCP integrations are optional upgrades, not requirements.

**Repo structure:**
```
pm-copartner/
├── Hello PM.md              ← You are here
├── README.md                ← Project overview
├── CONTRIBUTING.md          ← Contribution guidelines
├── 01-discovery/            ← User research synthesis
├── 02-planning/             ← Backlog prioritisation
├── 03-specs/                ← PRD auto-drafter
├── 04-analytics/            ← Weekly metrics digest
└── 05-launch/               ← Release notes generator
```

Each agent folder contains:
- `README.md` — what it does, when to use it, output format
- `prompt.md` — the Claude prompt (copy this and fill `[brackets]`)
- `setup.md` — minimal path (no tools) + connected path (MCP integrations)

---

## The 5 Agents at a Glance

| # | Agent | Input | Output | Run When |
|---|-------|-------|--------|----------|
| 01 | **Insight** | Raw interview notes (any format) | Structured insight report: themes, quotes, ranked opportunities | After research sprints, before planning |
| 02 | **Prioritize** | Backlog list + one-sentence OKR | Scored & ranked prioritisation brief with rationale per item | Weekly before sprint planning |
| 03 | **Blueprint** | Feature request (any format, even one sentence) | First-draft PRD: problem, users, metrics, scope, open questions | Always on / on demand |
| 04 | **Pulse** | This week's numbers + targets | RAG-status digest: metrics vs target, top movers, recommended actions | Weekly Monday or Friday EOD |
| 05 | **Ship** | Closed ticket list or sprint summary | User-facing release notes in your brand voice | Per release / per sprint close |

---

## 01 — Insight Agent

**File:** [`01-discovery/prompt.md`](./01-discovery/prompt.md)

**What it does:** Synthesises raw interview notes into a one-page insight report with top themes (3–7), supporting quotes per theme, ranked opportunity areas, and flagged contradictions.

**Minimum input:** Your interview notes in any format — bullet points, transcript, voice note, doc.

**Output format:**
```
# Research Synthesis — [Date / Sprint]
Interviews conducted: [N] | Date range: [start] – [end]

## Top Themes
### 1. [Theme] — [X of Y participants]
> "[Quote]" — Participant [N]
*Summary: one sentence*

## Ranked Opportunity Areas
| # | Opportunity | Frequency | Severity | Recommended Next Step |

## Contradictions & Outliers
## Suggested Next Steps
```

**Optional MCP integrations:** Notion (pull notes / save report), Google Drive (read/write docs), Linear (create issues from opportunities).

**Run frequency:** After each batch of 3+ interviews, before quarterly planning, before any prioritisation decision.

---

## 02 — Prioritize Agent

**File:** [`02-planning/prompt.md`](./02-planning/prompt.md)

**What it does:** Scores backlog items on Impact / Effort / Strategic Fit, computes a composite score (out of 10), ranks all items, writes a one-line rationale per item, flags quick wins and parking lot items.

**Minimum input:** A list of backlog items (paste from anywhere) + one sentence describing your current OKR or goal.

**Scoring weights (adjustable in prompt):**
- Impact: default weight 2
- Effort: default weight 1 (lower effort = higher score)
- Strategic fit: default weight 3

**Output format:**
```
# Prioritisation Brief — [Date / Sprint]
OKR / Focus: [goal] | Items reviewed: [N]

## Priority Ranking
| Rank | Item | Impact | Effort | Strategic Fit | Score | Rationale |

## ⚡ Quick Wins (Do First)
## 🅿️ Parking Lot (Low fit with current strategy)
## Notes
```

**Optional MCP integrations:** Linear (pull backlog), Jira (pull backlog), Notion (read OKRs / save output).

**Run frequency:** Weekly before sprint planning, before roadmap reviews, during backlog triage.

---

## 03 — Blueprint Agent

**File:** [`03-specs/prompt.md`](./03-specs/prompt.md)

**What it does:** Turns any feature request — a Slack message, email, ticket, one-liner — into a structured first-draft PRD. Flags every gap as an open question so nothing falls through the cracks.

**Minimum input:** The feature request text. Even one sentence works — the vaguer the input, the more open questions are surfaced (that's the point).

**Output format:**
```
# PRD: [Feature Name]
Status: Draft | Date: [date] | Request source: [Slack/Jira/Email/etc.] | Product area: [area]

## Problem
## Users
## Success Metrics (checkboxes)
## In Scope / Out of Scope
## Non-Goals
## Open Questions (checkboxes)
## Notes & Assumptions
```

**Optional MCP integrations:** Gmail (monitor inbound requests), Slack (monitor #feature-requests channel), Jira/Linear (pull new tickets), Notion (save PRD drafts).

**"Always on" options:**
1. Slack MCP + `/schedule` → daily check of #feature-requests
2. Email forward workflow → paste into Claude manually (30 seconds)
3. Batch: paste N requests at once, add "Draft a separate PRD for each"

**Run frequency:** On demand when any request comes in, once before each sprint to spec unspecced items.

---

## 04 — Pulse Agent

**File:** [`04-analytics/prompt.md`](./04-analytics/prompt.md)

**What it does:** Compares metrics to targets, assigns RAG status (🟢 at/above target, 🟡 within 10% below, 🔴 >10% below or significant negative trend), calculates WoW change, identifies top movers, gives one specific action per red metric, writes a 2–3 sentence executive summary.

**Minimum input:** This week's numbers + targets (even rough ones like "DAU should be above 4,000").

**No formal targets?** Use prior week as baseline — add: *"Use the prior week's numbers as the baseline and flag any metric that moved more than 10% in either direction."*

**Output format:**
```
# Weekly Metrics Digest — Week of [Date]

## Summary (2–3 sentences)

## Metrics vs Target
| Metric | Target | Actual | Status | WoW Change |

## Top Movers
## Recommended Actions
## Anomalies / Flags
## Data Sources
```

**Optional MCP integrations:** Notion (read KPI targets / save digest), Google Drive (read CSV exports / save report), Slack (post digest to channel), Linear/Jira (correlate metrics with shipped work).

**Scheduler tip:** This agent delivers most value automated weekly. Connect Notion + Drive via MCP, use `/schedule` in Claude Desktop → every Monday at 8am.

**Run frequency:** Weekly (Mon morning or Fri EOD), daily for first week post major release, monthly batch for board/investor reporting.

---

## 05 — Ship Agent

**File:** [`05-launch/prompt.md`](./05-launch/prompt.md)

**What it does:** Takes a list of closed tickets or sprint summary, ignores internal-only items (infra, chores), rewrites each user-facing item with a plain-language title and 1–2 benefit-focused sentences, groups features vs fixes, writes a one-sentence release summary. Flags uncertain items as `[NEEDS PM REVIEW]`.

**Minimum input:** A list of what shipped (bullet points, ticket titles, sprint summary, memory).

**Brand voice:** Describe in one sentence in the prompt — or skip for clear/plain-English default.

| Audience | Voice example |
|----------|---------------|
| SMB customers | "Friendly, short sentences, no jargon, non-technical." |
| Developers | "Direct, precise, technical terms OK." |
| Internal team | "Matter-of-fact, bullet points fine." |
| Enterprise | "Professional, measured, avoid hype, emphasise reliability." |

**Output format:**
```
# [Product] Release Notes — [Version / Sprint]
Released: [Date]

## What's New in This Release (one-sentence summary)

### ✨ New Features
#### [User-facing title]
[1–2 sentences. What changed. Why the user cares. In brand voice.]

### 🐛 Bug Fixes & Improvements
- **[Fix]:** one sentence

---
*Have questions? [support channel]*
```

**Optional MCP integrations:** Jira (pull closed sprint), Linear (pull closed cycle), Notion (read tone-of-voice / save notes), Google Drive (save notes), Gmail (send notes).

**Run frequency:** Per sprint close, on demand for hotfixes, per major release (consider writing internal + external versions separately).

---

## How to Run Any Agent (3 Steps)

1. **Open** `[agent-folder]/prompt.md`
2. **Copy** the full prompt into Claude (claude.ai or Claude Desktop)
3. **Replace** all `[bracket]` placeholders with your data — delete any option blocks you're not using

That's it. No accounts, no setup, no integrations required unless you want automation.

---

## MCP Integrations Quick Reference

All integrations are **optional**. Use the minimal path first; add connectors when you want automation.

| Tool | MCP Server | Used By |
|------|-----------|---------|
| Notion | `@notionhq/notion-mcp-server` | All 5 agents (read/write docs, OKRs, databases) |
| Linear | `linear-mcp` | 01 (create issues), 02 (pull backlog), 03 (pull requests), 05 (pull sprint) |
| Jira | `jira-mcp` / Atlassian MCP | 02 (pull backlog), 03 (pull tickets), 05 (pull sprint) |
| Google Drive | `@google/drive-mcp` | 01, 04, 05 (read exports, save reports) |
| Slack | Slack MCP | 03 (monitor #feature-requests), 04 (post digest) |
| Gmail | Gmail MCP | 03 (monitor inbound), 05 (send release notes) |

**No tool?** Every agent has a copy-paste fallback listed in its `setup.md`.

---

## Automation / Scheduling

Use Claude Desktop's `/schedule` command to automate any agent:
1. Connect data sources via MCP
2. Paste the prompt with the MCP pull instruction
3. Type `/schedule` → set frequency (e.g. "Every Monday at 9am")

| Agent | Recommended schedule |
|-------|---------------------|
| 01 Insight | Manual trigger after research sessions |
| 02 Prioritize | Every Monday before planning meeting |
| 03 Blueprint | Daily or on demand |
| 04 Pulse | Every Monday 8am or Friday 4pm |
| 05 Ship | Per sprint close (manual trigger) |

---

## Contributing

See [`CONTRIBUTING.md`](./CONTRIBUTING.md). Key rules:
- Prompts must work with **copy-paste only** — no hard integration dependencies
- Use `[bracket]` placeholders for everything user-specific
- Every prompt needs a clear output format and a Tips section (2–3 variations)
- To propose a new agent: open a GitHub issue using the **New Agent Proposal** template first

Issue templates: `.github/ISSUE_TEMPLATE/new-agent.yml`, `prompt-issue.yml`, `setup-help.yml`
