# 03 — Blueprint: PRD Auto-Drafter

## What It Does

Takes a feature request — from Slack, email, a Jira ticket, Linear issue, a voice note transcription, or a sticky note — and drafts a **structured PRD (Product Requirements Document)** ready for PM review.

The PRD covers:
- **Problem statement** — what user pain or business need this addresses
- **Users** — who this is for and what they're trying to do
- **Success metrics** — how you'll know it worked
- **Scope** — what's in, what's explicitly out
- **Non-goals** — what this does not solve
- **Open questions** — what needs to be decided before build

## Why This Exists

PRDs get written too late, too fast, or not at all. This agent gets a first draft done the moment a request arrives — before engineers ask, before the meeting, before the request goes cold.

## When to Run

- **Always on** — whenever a new feature request comes in
- On demand — when you have a backlog of unspecced tickets

## Output Format

```
# PRD: [Feature Name]

**Status:** Draft  
**Author:** [PM Name]  
**Date:** [Date]  
**Request source:** [Slack / Jira / Email / etc.]

---

## Problem
[What problem are we solving and for whom?]

## Users
[Who is affected? What are they trying to do?]

## Success Metrics
- [Metric 1]
- [Metric 2]

## Scope
**In scope:**
- [...]

**Out of scope:**
- [...]

## Non-Goals
- [...]

## Open Questions
- [ ] [Question that must be answered before build]
```

## Minimum Requirements

- The feature request text (any format — even one sentence)
- Nothing else required; the agent will flag gaps as open questions

## With Integrations

- Monitor **Slack** channel for new requests → use Slack MCP (or forward messages manually)
- Pull new **Jira / Linear** tickets → use respective MCP
- Post draft PRD to **Notion** → use Notion MCP
- Notify PM via **Gmail / Slack** → use respective connector

See [setup.md](./setup.md) for details.
