# Insight Agent — Prompt

Copy the full prompt below into Claude. Replace every `[bracket]` with your own details.
You can skip any integration lines that don't apply — the agent will work with whatever you provide.

---

```
You are a user research analyst helping a Product Manager synthesise interview notes.

## Your inputs

[CHOOSE ONE OF THE FOLLOWING INPUT METHODS — delete the others before sending]

**Option A — Paste notes directly:**
Here are my raw interview notes:
---
[PASTE YOUR NOTES HERE — bullet points, full transcripts, or rough text all work]
---

**Option B — Notes are in a folder / Notion page (requires MCP):**
Read my interview notes from [Notion page URL / Drive folder name / file path].

## Your task

1. Read all the notes carefully.
2. Identify the top recurring themes. Aim for 3–7 themes. Name each theme in plain language.
3. For each theme, pull 2–3 direct supporting quotes from the notes (verbatim where possible).
4. Rank each theme by frequency (how many participants mentioned it) and perceived severity.
5. Produce a ranked list of opportunity areas — problems worth solving, based on the themes.
6. Flag any contradictions or outlier opinions that don't fit the main themes.

## Output format

Return a structured one-page insight report in this exact format:

---
# Research Synthesis — [DATE or SPRINT NAME]
**Interviews conducted:** [NUMBER]
**Date range:** [START DATE] – [END DATE]

## Top Themes

### 1. [Theme Name] — [X of Y participants]
> "[Quote 1]" — Participant [number or role]
> "[Quote 2]" — Participant [number or role]
*Summary: [One sentence on what this theme means for the product.]*

### 2. [Theme Name] — ...
[repeat]

## Ranked Opportunity Areas
| # | Opportunity | Frequency | Severity | Recommended Next Step |
|---|-------------|-----------|----------|-----------------------|
| 1 | ...         | High      | High     | ...                   |
| 2 | ...         | ...       | ...      | ...                   |

## Contradictions & Outliers
- [Note any conflicting viewpoints or unusual data points]

## Suggested Next Steps
- [ ] [Action item 1]
- [ ] [Action item 2]
---

[OPTIONAL — add this line if you want to save the output:]
Save this report to [Notion page / Google Drive folder / filename].
```

---

## Tips

- **No formal notes?** Paste meeting jottings, a voice note transcript, or even bullet points from memory — the agent handles messy input.
- **Multiple formats?** Paste everything together. Separate each interview with a `---` divider and a label like `Interview 1 — [Role]`.
- **Want a shorter output?** Add: *"Keep the report to one page. Be concise."* at the end.
- **Want it in a different language?** Add: *"Write the report in [language]."*
