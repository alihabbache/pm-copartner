# Pulse Agent — Tool Setup

This agent works with or without any integrations. Start with the minimal path; add connectors when you're ready.

---

## Minimal Path (No integrations needed)

**What you need:** This week's numbers and your targets — in any format.

**How to use:**
1. Open your analytics tool (Google Analytics, Mixpanel, PostHog, Amplitude, a spreadsheet — anything)
2. Copy or screenshot the key numbers you care about
3. Write out your targets (even rough ones like *"DAU should be above 4,000"*)
4. Paste the prompt from `prompt.md` into Claude
5. Paste your metrics where indicated
6. Run

No integrations required. If you can type a number, the agent can analyse it.

---

## Connected Path (With MCP integrations)

### Notion (Read KPI targets + Save digest)
- **MCP server:** `@notionhq/notion-mcp-server`
- **What it enables:** Pull your KPI targets from a Notion table; save the weekly digest back to Notion
- **Setup:** [Notion MCP setup guide](https://github.com/makenotion/notion-mcp-server)
- **What to add in prompt:** *"Read our KPI targets from [Notion page URL]."*
- **Pro tip:** Keep all your KPI targets in one Notion page — every digest pulls from the same source and stays consistent

### Google Drive (Analytics exports + Save digest)
- **MCP server:** Google Drive MCP
- **What it enables:** Read analytics CSV exports saved to Drive; save the digest report to Drive
- **What to add in prompt:** *"Read this week's analytics export from [file name / folder] in Google Drive."*

### Slack (Post digest)
- **MCP server:** Slack MCP
- **What it enables:** Post the finished digest to a Slack channel automatically
- **What to add in prompt:** *"Post this digest to the [#product-metrics / #team] Slack channel."*

### Linear / Jira (Correlate metrics with shipped work)
- **Optional enhancement:** If you want to explain metric movements by correlating with what shipped, add: *"Read what was closed in [Linear / Jira] this week and note any correlation with the metric changes."*

---

## Tool Alternatives

| If you don't have... | Use instead |
|----------------------|-------------|
| Formal analytics tool | Paste numbers from any source — even a spreadsheet or gut estimate |
| Defined KPI targets | Use previous week as baseline; agent flags moves > 10% |
| Notion | Type your targets directly in the prompt |
| Slack | Copy-paste the digest into email, Notion, or wherever the team reads updates |
| Google Analytics | PostHog, Mixpanel, Amplitude, or any tool you export from — paste the CSV or numbers |

---

## Scheduler Setup (Recommended for this agent)

This agent delivers the most value when it runs automatically every week.

**Using Claude's `/schedule` command:**
1. Connect your data sources via MCP (Notion for targets, Drive for exports)
2. Paste the prompt from `prompt.md`
3. Type `/schedule` in Claude Desktop
4. Set frequency: *"Every Monday at 8am"* or *"Every Friday at 4pm"*
5. On each run, Claude pulls fresh data, produces the digest, and optionally posts it

**Manual weekly habit (no MCP):**
1. Every Monday morning, open your analytics tool
2. Copy this week's key numbers
3. Paste prompt + numbers into Claude
4. Copy the digest and post to `#product-metrics` or email to team
5. Total time: under 5 minutes

---

## Recommended Run Frequency

| Scenario | Frequency |
|----------|-----------|
| Standard weekly reporting | Every Monday morning or Friday EOD |
| Post-release monitoring | Daily for the first week after a major release |
| Board / investor reporting | Pull 4 weeks of data at once for a monthly view |
