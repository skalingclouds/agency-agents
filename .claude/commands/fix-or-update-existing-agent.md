---
name: fix-or-update-existing-agent
description: Workflow command scaffold for fix-or-update-existing-agent in agency-agents.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /fix-or-update-existing-agent

Use this workflow when working on **fix-or-update-existing-agent** in `agency-agents`.

## Goal

Fixes, expands, or updates an existing agent's documentation, such as correcting errors, expanding sections, or aligning with templates.

## Common Files

- `engineering/engineering-*.md`
- `specialized/specialized-*.md`
- `marketing/marketing-*.md`
- `academic/academic-*.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit the existing agent markdown file in its division folder.
- Make corrections, expand sections, or update formatting/frontmatter as needed.
- Optionally, mention the update in the commit message for traceability.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.