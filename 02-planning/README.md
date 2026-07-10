# 02 — Prioritize: Roadmap Prioritisation Brief

## What It Does

Takes your backlog — from Jira, Linear, a spreadsheet, or a plain list — cross-references it against your strategy, OKRs, or "north star" doc, and outputs a **scored, ranked prioritisation brief** with a one-line rationale per item.

Scoring is based on three dimensions you can adjust:
- **Impact** — how much does this move the key metric?
- **Effort** — rough size/complexity estimate
- **Strategic fit** — how directly does this serve current OKRs?

## Why This Exists

Backlog grooming is often gut-feel dressed up as data. This agent forces the comparison to be explicit and auditable — every rank has a written reason.

## When to Run

- Weekly, at the start of sprint planning
- Before roadmap review meetings
- When the backlog has grown and needs a triage pass

## Output Format

```
# Prioritisation Brief — Week of [Date]

| Rank | Item | Impact | Effort | Strategic Fit | Score | Rationale |
|------|------|--------|--------|---------------|-------|-----------|
| 1    | ...  | High   | Low    | Direct        | 9/10  | ...       |
| 2    | ...  | ...    | ...    | ...           | ...   | ...       |

## Items Flagged for Removal / Parking
- [Item] — reason

## Notes
- OKR used: [...]
- Strategy doc referenced: [...]
```

## Minimum Requirements

- A list of backlog items (copy-paste from any tool, or just type them out)
- A brief statement of your current goal or OKR (one sentence is enough)

## With Integrations

- Pull backlog from **Jira** → use Jira MCP
- Pull backlog from **Linear** → use Linear MCP
- Read OKRs from **Notion** → use Notion MCP
- Save output to **Notion** or **Excel/Sheets** → use respective connector

See [setup.md](./setup.md) for details.
