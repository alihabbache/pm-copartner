# Contributing to PM CoPartner

First off — thank you. This project is only as useful as the prompts inside it, and the prompts only get better through real-world use.

---

## What You Can Contribute

### 1. Improve an existing prompt
If a prompt didn't work well for your use case, or you found a better phrasing — submit a PR with the change and a one-line explanation of what you improved and why.

### 2. Add a tool-specific setup guide
If you've got a working setup with a tool not currently covered (e.g. Confluence, Asana, GitHub Issues, Shortcut, Productboard), add a section to the relevant `setup.md`.

### 3. Fix something broken
If an output format doesn't render correctly, a link is dead, or instructions are unclear — open a PR.

### 4. Propose a new agent
If there's a PM workflow not covered by the existing 5 agents, open an issue first using the **New Agent Proposal** template before building. This keeps discussion open before effort is spent.

### 5. Share a real-world example
If you've used an agent and got a useful output, you can add a `examples/` folder inside the agent directory with an anonymised sample input/output. These help other PMs calibrate expectations.

---

## How to Submit Changes

1. Fork the repository
2. Create a branch: `git checkout -b improve-discovery-prompt`
3. Make your change
4. Submit a pull request with a clear title and description:
   - What you changed
   - Why (what problem it solves or what it improves)
   - If it's a prompt change: what input you tested it on and what the output looked like

---

## Prompt Contribution Guidelines

Good prompts in this repo share these properties:

- **Tool-agnostic by default.** The prompt must work with just copy-paste into Claude — integrations are optional.
- **`[bracket]` placeholders for everything user-specific.** Never hardcode a tool name, URL, or project name.
- **A clear output format.** Every prompt should specify exactly what the output should look like.
- **Tips section.** Include at least 2–3 tips for common variations (shorter output, different audience, batch processing, etc.).

If you're updating a prompt, test it with at least one real input before submitting.

---

## Setup Guide Contribution Guidelines

Good setup guides:

- Lead with the **minimal path** — no integrations, just paste
- List integrations in order of most common to least common
- Include the **MCP server name or repo link** for each integration
- Include the **exact prompt addition** the user needs to make for each integration
- Include a **tool alternatives table** for PMs who don't have that tool

---

## What We're Not Looking For

- Prompts that only work with a specific paid tool
- Contributions that add new dependencies without a fallback
- Breaking changes to the existing folder structure without discussion
- Content promoting specific vendors, tools, or services

---

## Questions?

Open an issue — it doesn't have to be a bug. Discussion is welcome.
