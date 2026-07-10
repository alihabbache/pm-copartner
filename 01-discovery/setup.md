# Insight Agent — Tool Setup

This agent works with or without any integrations. Start with the minimal path; add connectors when you're ready.

---

## Minimal Path (No integrations needed)

**What you need:** Your interview notes, in any format.

**How to use:**
1. Copy your notes — from a doc, email, Notion, Notion export, voice transcript, even meeting jottings
2. Open [claude.ai](https://claude.ai) or Claude Desktop
3. Paste the prompt from `prompt.md`
4. Paste your notes where indicated
5. Run

That's it. No accounts, no connectors, no setup.

---

## Connected Path (With MCP integrations)

Use these to automate input/output so the agent can pull notes and save results without manual copy-paste.

### Notion (Read notes + Save report)
- **MCP server:** `@notionhq/notion-mcp-server`
- **What it enables:** Pull interview notes from a Notion page; save the synthesis report back to Notion
- **How to set up:** [Notion MCP setup guide](https://github.com/makenotion/notion-mcp-server)
- **What to add in prompt:** Replace the paste block with: *"Read my interview notes from [Notion page URL]."*
- **To save output:** Add: *"Save this report to [Notion page URL / page name]."*

### Google Drive (Read docs + Save report)
- **MCP server:** `@google/drive-mcp` or use Google Drive API via Claude
- **What it enables:** Pull notes from Drive docs or folders; save the output report to Drive
- **How to set up:** [Google Drive MCP](https://github.com/google-gemini/generative-ai-docs) or enable via Claude Desktop settings
- **What to add in prompt:** *"Read my interview notes from the [folder name] folder in Google Drive."*
- **To save output:** *"Save this report to [folder name] in Google Drive as [filename].md"*

### Linear (Track opportunities as issues)
- **MCP server:** `linear-mcp` or use Linear API
- **What it enables:** Create Linear issues directly from the ranked opportunity areas
- **What to add in prompt:** *"For each opportunity in the ranked list, create a Linear issue in [team name] with the label 'research-insight'."*

---

## Tool Alternatives

| If you don't have... | Use instead |
|----------------------|-------------|
| Notion | Paste notes directly into Claude |
| Google Drive | Copy-paste notes; save output by copy-pasting Claude's response |
| Linear | Manually add opportunities to whatever backlog tool you use |
| Any tool at all | Everything can be done by copy-paste — this agent has zero hard dependencies |

---

## Scheduler Setup (Optional)

Run this agent automatically before every planning meeting or at the end of each research sprint.

**Using Claude's `/schedule` command:**
1. Open Claude Desktop
2. Paste the prompt from `prompt.md`
3. Type `/schedule`
4. Set frequency: *"Run once after I paste notes"* (manual trigger) or *"Run every [X] days"* (if pulling from a connected source)

**Manual trigger workflow:**
- Keep the prompt saved in a doc or note
- After each research session, paste notes + run — takes under 2 minutes

---

## Recommended Run Frequency

| Scenario | Frequency |
|----------|-----------|
| Active research sprint | After each batch of 3+ interviews |
| Quarterly planning | Once before the planning cycle starts |
| On-demand | Any time you're making a prioritisation decision and want evidence |
