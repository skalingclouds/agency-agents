---
name: add-new-agent
description: Workflow command scaffold for add-new-agent in agency-agents.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-new-agent

Use this workflow when working on **add-new-agent** in `agency-agents`.

## Goal

Adds a new agent to a division (e.g., engineering, marketing, specialized, academic) by creating a new agent markdown file, and often updating the README to include the new agent in the division table.

## Common Files

- `README.md`
- `engineering/engineering-*.md`
- `marketing/marketing-*.md`
- `specialized/specialized-*.md`
- `academic/academic-*.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create a new markdown file for the agent in the appropriate division folder (e.g., engineering/, marketing/, specialized/, academic/).
- Add agent details following the standard template.
- Update README.md to include the new agent in the relevant division table (optional, but common).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.