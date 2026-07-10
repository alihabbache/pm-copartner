# Launch Agent — Tool Setup

This agent works with or without any integrations. Start with the minimal path; add connectors when you're ready.

---

## Minimal Path (No integrations needed)

**What you need:** A list of what shipped — ticket titles, bullet points, a sprint summary, or even a rough memory of what went out.

**How to use:**
1. List what shipped this sprint or release (copy from Jira/Linear, or just type it out)
2. Write one sentence describing your brand voice (or skip it — the agent defaults to clear and plain English)
3. Paste the prompt from `prompt.md` into Claude
4. Fill in the release details
5. Run

No tools required. If you know what shipped, the agent can write the notes.

---

## Connected Path (With MCP integrations)

### Jira (Pull closed sprint tickets)
- **MCP server:** Jira MCP (Atlassian)
- **What it enables:** Automatically pull all tickets closed in the current sprint without manual listing
- **What to add in prompt:** *"Read closed tickets from Jira sprint [sprint name] in project [project key]."*

### Linear (Pull closed sprint / cycle issues)
- **MCP server:** `linear-mcp`
- **What it enables:** Pull completed issues from a Linear sprint/cycle
- **What to add in prompt:** *"Read closed issues from Linear sprint [sprint number] for team [team name]."*

### Notion (Read tone-of-voice guide + Save notes)
- **MCP server:** `@notionhq/notion-mcp-server`
- **What it enables:** Read your brand tone-of-voice doc from Notion; save the release notes as a Notion page for review
- **Setup:** [Notion MCP setup guide](https://github.com/makenotion/notion-mcp-server)
- **What to add in prompt:** *"Read our tone-of-voice guide from [Notion page URL]. Save the release notes as a new Notion page in [space/database name]."*

### Google Drive (Save release notes)
- **MCP server:** Google Drive MCP
- **What it enables:** Save the finished release notes to a Drive folder
- **What to add in prompt:** *"Save these release notes to [folder name] in Google Drive as [filename].md"*

### Gmail (Send release notes)
- **MCP server:** Gmail MCP
- **What it enables:** Send the finished release notes via email
- **What to add in prompt:** *"Send these release notes via Gmail to [email address / mailing list]."*

---

## Tool Alternatives

| If you don't have... | Use instead |
|----------------------|-------------|
| Jira / Linear | List shipped items as bullet points — from memory, a meeting note, or a Slack thread |
| Notion tone guide | Describe your voice in one sentence directly in the prompt |
| Google Drive | Copy-paste Claude's output into any doc tool |
| Gmail | Copy the release notes into any email client or communication tool |
| Any tool | A bulleted list of what shipped is all you need |

---

## Brand Voice Tips

You don't need a formal tone-of-voice doc. Describe it in plain English in the prompt:

| Audience | Example voice description |
|----------|--------------------------|
| SMB customers | "Friendly and encouraging. Short sentences. No jargon. Assume they're not technical." |
| Developer users | "Direct and precise. Technical terms are fine. Include relevant detail." |
| Internal team | "Matter-of-fact. Bullet points are fine. Engineers will read this." |
| Enterprise customers | "Professional and measured. Avoid hype. Emphasise reliability and control." |

---

## Scheduler Setup

**Per-release trigger (recommended):**
- No scheduler needed — run this manually at the end of every sprint or release
- Takes under 2 minutes from ticket list to finished release notes

**Automated end-of-sprint run (with MCP):**
1. Connect Jira or Linear MCP
2. Paste the prompt with the MCP pull instruction
3. Type `/schedule` in Claude Desktop
4. Set trigger: *"Run at the end of each sprint on [day]"*

---

## Recommended Run Frequency

| Scenario | Frequency |
|----------|-----------|
| Regular sprint cadence | Per sprint close (weekly or bi-weekly) |
| Hotfix / patch release | On demand, immediately after the fix ships |
| Major release | Per release — consider writing both an internal and external version |
