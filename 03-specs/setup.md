# Specs Agent — Tool Setup

This agent works with or without any integrations. Start with the minimal path; add connectors when you're ready.

---

## Minimal Path (No integrations needed)

**What you need:** The feature request text — any format, any length.

**How to use:**
1. Find the feature request — a Slack message, email, meeting note, sticky note, voice transcript, one-liner — anything
2. Paste the prompt from `prompt.md` into Claude
3. Paste the request where indicated
4. Run

The agent will draft the PRD and flag every gap as an open question. You don't need to write a well-formed request — the vaguer the input, the more questions the agent will surface, which is exactly what you want before a spec conversation.

---

## Connected Path (With MCP integrations)

### Gmail (Monitor inbound feature requests)
- **MCP server:** Gmail MCP via Claude Desktop
- **What it enables:** Read emails from a specific label or sender as feature request inputs
- **What to add in prompt:** *"Read unread emails from [label / sender] in Gmail and treat each as a feature request."*

### Slack (Monitor feature request channel)
- **MCP server:** Slack MCP
- **What it enables:** Read new messages from a Slack channel (e.g. `#feature-requests`) since a given date
- **Setup:** Requires a Slack API token and channel ID
- **What to add in prompt:** *"Read new messages from the [#channel-name] Slack channel since [DATE]. Treat each message as a feature request."*

### Jira (Pull new inbound tickets)
- **MCP server:** Jira MCP
- **What it enables:** Pull newly created tickets from a Jira project as feature request inputs
- **What to add in prompt:** *"Read new Jira tickets created in [project key] since [DATE]."*

### Linear (Pull new issues)
- **MCP server:** `linear-mcp`
- **What it enables:** Pull new Linear issues as feature request inputs
- **What to add in prompt:** *"Read new Linear issues in [team name] created since [DATE]."*

### Notion (Save PRD drafts)
- **MCP server:** `@notionhq/notion-mcp-server`
- **What it enables:** Post the drafted PRD directly to a Notion page or database
- **What to add in prompt:** *"Post this PRD draft to the [product / specs] Notion space."*

---

## Tool Alternatives

| If you don't have... | Use instead |
|----------------------|-------------|
| Slack | Forward the email or copy-paste the message |
| Jira / Linear | Paste the request text directly |
| Notion | Copy Claude's output into any doc tool (Google Docs, Confluence, etc.) |
| A structured request | Even one sentence works — the agent will draft and flag what's missing |

---

## "Always On" Setup

This agent is most powerful when it's always on — drafting PRDs the moment a request comes in.

**Option 1 — Slack trigger (with MCP):**
1. Connect Slack MCP in Claude Desktop
2. Set a `/schedule` to run daily or on demand
3. Claude checks `#feature-requests` and drafts PRDs for anything new

**Option 2 — Email forward workflow (no MCP):**
1. When you receive a feature request by email, forward it to yourself with the subject "PRD request"
2. Paste it into Claude with the prompt — takes 30 seconds
3. PRD is drafted before your next standup

**Option 3 — Batch processing:**
- Collect requests for a week, paste them all at once
- Add: *"Here are [N] feature requests. Draft a separate PRD for each."*

---

## Recommended Run Frequency

| Scenario | Frequency |
|----------|-----------|
| Active request intake | Daily or on demand when requests arrive |
| Sprint planning prep | Once before each sprint to spec any unspecced items |
| Backlog cleanup | On demand for any tickets that have no PRD |
