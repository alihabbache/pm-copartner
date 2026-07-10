# Prioritize Agent — Tool Setup

This agent works with or without any integrations. Start with the minimal path; add connectors when you're ready.

---

## Minimal Path (No integrations needed)

**What you need:** A list of backlog items and a one-sentence description of your current goal.

**How to use:**
1. Copy your backlog — from Jira, Linear, Notion, a spreadsheet, or just type it out
2. Write one sentence describing your current OKR or priority focus (e.g. *"Reduce churn for SMB users this quarter"*)
3. Paste the prompt from `prompt.md` into Claude
4. Fill in the `[bracket]` fields
5. Run

No integrations required. If you can paste a list, the agent can prioritise it.

---

## Connected Path (With MCP integrations)

### Linear (Pull backlog)
- **MCP server:** `linear-mcp`
- **What it enables:** Automatically pull open issues from a Linear team or project
- **Setup:** [Linear MCP](https://github.com/linear/linear-mcp) — requires a Linear API key
- **What to add in prompt:** *"Read the open backlog items from Linear team [team name]."*

### Jira (Pull backlog)
- **MCP server:** `jira-mcp` or Atlassian MCP
- **What it enables:** Pull open tickets from a Jira project
- **Setup:** Requires a Jira API token + project URL
- **What to add in prompt:** *"Read the open backlog items from Jira project [project key]."*

### Notion (Read OKRs + Save output)
- **MCP server:** `@notionhq/notion-mcp-server`
- **What it enables:** Pull OKRs/strategy docs from Notion; save the prioritisation brief back
- **Setup:** [Notion MCP setup guide](https://github.com/makenotion/notion-mcp-server)
- **What to add in prompt:** *"Read our strategy and OKRs from [Notion page URL]."*

### Excel / Google Sheets (Backlog input or output)
- **Option:** Export your backlog as CSV, paste directly into Claude
- **For output:** Ask Claude to format the table as CSV, then paste into your spreadsheet
- **No MCP needed** for this path — copy-paste works fine

---

## Tool Alternatives

| If you don't have... | Use instead |
|----------------------|-------------|
| Jira | Paste ticket titles as a bullet list |
| Linear | Paste issue titles from any source |
| Notion for OKRs | Type your goal in one sentence directly in the prompt |
| Spreadsheet | Copy-paste the ranked table from Claude's output |

---

## Scheduler Setup (Optional)

**Weekly automated run:**
1. Connect your backlog tool via MCP
2. Paste the prompt with the MCP pull instruction
3. Type `/schedule` in Claude Desktop
4. Set frequency: *"Run every Monday at 9am"*
5. Claude will pull the latest backlog, score it, and produce a fresh brief

**Manual weekly habit:**
- Keep the prompt bookmarked
- Every Monday, update your backlog paste and run — takes 3 minutes

---

## Recommended Run Frequency

| Scenario | Frequency |
|----------|-----------|
| Sprint planning | Weekly, before the planning meeting |
| Quarterly roadmap review | Once at the start of each quarter |
| Backlog triage | Any time the backlog has grown and needs a pass |
