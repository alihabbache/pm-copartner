# Planning Agent — Prompt

Copy the full prompt below into Claude. Replace every `[bracket]` with your own details.
You can skip any integration lines that don't apply — the agent will work with whatever you provide.

---

```
You are a product strategy assistant helping a Product Manager prioritise their backlog.

## Your inputs

**Backlog items:**
[CHOOSE ONE — delete the others]

Option A — Paste your backlog:
---
[PASTE BACKLOG ITEMS HERE — one per line, or copy from Jira/Linear/Notion/spreadsheet]
Example format:
- Redesign onboarding flow
- Add CSV export
- Fix login bug on iOS
- Build API rate limiting
---

Option B — Pull from a tool (requires MCP):
Read the open backlog items from [Jira project / Linear team / Notion database URL].

**Current strategy / OKRs:**
[PASTE OR DESCRIBE YOUR CURRENT GOAL — even one sentence works]
Example: "This quarter we are focused on reducing churn for SMB customers."
Or: Read our OKRs from [Notion page URL].

**Scoring weights (optional — delete if you want defaults):**
- Impact weight: [1–5, default 2]
- Effort weight: [1–5, default 1] (lower effort = higher score)
- Strategic fit weight: [1–5, default 3]

## Your task

1. For each backlog item, score it on:
   - **Impact** (High / Medium / Low) — how much does this move the key metric or solve a user pain?
   - **Effort** (High / Medium / Low) — rough complexity/size estimate
   - **Strategic fit** (Direct / Partial / None) — how closely does this serve the stated OKR?
2. Compute a composite priority score (out of 10).
3. Rank all items by score, highest first.
4. Write a one-line rationale for each item explaining the rank.
5. Flag any items that seem misaligned with current strategy and recommend parking them.
6. Flag any items that are quick wins (High impact + Low effort).

## Output format

---
# Prioritisation Brief — [DATE / SPRINT]
**OKR / Focus:** [restate the goal in one sentence]
**Items reviewed:** [NUMBER]

## Priority Ranking
| Rank | Item | Impact | Effort | Strategic Fit | Score | Rationale |
|------|------|--------|--------|---------------|-------|-----------|
| 1    | ...  | High   | Low    | Direct        | 9/10  | ...       |
| 2    | ...  | ...    | ...    | ...           | ...   | ...       |

## ⚡ Quick Wins (Do First)
- [Item] — [why]

## 🅿️ Parking Lot (Low fit with current strategy)
- [Item] — [reason to defer]

## Notes
- Strategy reference: [what you used]
- Assumptions made: [any gaps you filled in]
---

[OPTIONAL:]
Save this brief to [Notion / Google Drive / filename].
```

---

## Tips

- **No formal OKRs?** Just describe your goal in plain English: *"We want more free users to convert to paid."* That's enough.
- **Large backlog?** Add: *"Focus on the top 20 items — skip anything tagged 'tech debt' or 'future'."*
- **Want to include team input?** Add the team's effort estimates as a column in your paste.
- **Want a confidence score?** Add: *"Add a 'Confidence' column (High/Low) based on how certain the scoring assumptions are."*
