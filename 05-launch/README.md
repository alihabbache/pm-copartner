# 05 — Ship: Release Notes Generator

## What It Does

Takes the output of a completed sprint — closed tickets, a changelog, a list of shipped items, or a sprint summary — and writes **user-facing release notes** in your brand voice:

- **Summary** — what this release is about in one sentence
- **What changed** — each feature/fix explained for a non-technical user
- **Why it matters** — the benefit to the user, not the implementation detail
- Formatted for Notion, email, in-app changelog, or blog post

## Why This Exists

Release notes written by engineers are for engineers. This agent writes them for users — in plain language, in your tone, before anyone asks.

## When to Run

- **Per release / per sprint close**
- Any time you ship something and need to communicate it externally or internally

## Output Format

```
# Release Notes — [Product Name] [Version / Sprint]
**Released:** [Date]

## What's New

### [Feature / Fix Title]
[One to two sentences explaining what changed and why the user will care.]

### [Feature / Fix Title]
[...]

## Bug Fixes & Improvements
- [Fix 1]
- [Fix 2]

---
*Questions? Reach out at [support channel].*
```

## Minimum Requirements

- A list of what shipped (ticket titles, bullet points, or a sprint summary — anything works)
- Optionally: a sentence describing your brand voice (e.g. "friendly and direct, no jargon")

## With Integrations

- Pull closed **Jira** tickets → use Jira MCP
- Pull closed **Linear** sprint → use Linear MCP
- Read tone-of-voice guide from **Notion** → use Notion MCP
- Save to **Google Drive** and post as Notion page → use respective connectors
- Send via **Gmail** → use Gmail MCP

See [setup.md](./setup.md) for details.
