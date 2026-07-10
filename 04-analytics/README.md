# 04 — Analytics: Weekly Metrics Digest

## What It Does

Takes your product metrics — from an analytics export, a spreadsheet, a Notion table, or a plain data paste — compares them to your targets, and produces a **concise weekly digest** with:

- **Key metrics vs target** with RAG (Red / Amber / Green) status
- **Top movers** — what changed most week-over-week
- **Notable regressions** — what dropped and needs attention
- **One recommended action per flagged metric**

## Why This Exists

Weekly reporting is one of the most time-consuming, low-value PM tasks. This agent turns raw numbers into a stakeholder-ready summary in minutes, not an afternoon.

## When to Run

- Weekly — every Monday morning or Friday EOD
- After a major release, to catch early signals
- Any time a stakeholder asks "how are we doing?"

## Output Format

```
# Weekly Metrics Digest — Week of [Date]

## Summary
[2–3 sentence headline on the week]

## Metrics vs Target
| Metric         | Target | Actual | Status | WoW Change |
|----------------|--------|--------|--------|------------|
| [Metric]       | [X]    | [Y]    | 🟢     | +3%        |
| [Metric]       | [X]    | [Y]    | 🔴     | -8%        |

## Top Movers
- 📈 [Metric] up [X]% — possible cause: [...]
- 📉 [Metric] down [X]% — possible cause: [...]

## Recommended Actions
1. [Metric in red] → [Specific suggested action]
2. ...

## Notes
- Data source: [GA / Mixpanel / CSV / etc.]
- KPI reference: [Notion page / doc / inline]
```

## Minimum Requirements

- This week's numbers (paste from any tool, export a CSV, or type them out)
- Your targets for each metric (even rough ones)

## With Integrations

- Pull analytics from **Google Analytics / Mixpanel export** → paste CSV or use connector
- Read KPI targets from **Notion** → use Notion MCP
- Post digest to **Slack** → use Slack MCP or copy-paste into `#product-metrics`
- Save report to **Google Drive** → use Drive MCP

See [setup.md](./setup.md) for details.
