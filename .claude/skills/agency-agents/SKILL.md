```markdown
# agency-agents Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns and workflows for contributing to the `agency-agents` TypeScript repository. The project manages a roster of "agents" (roles or personas) organized by division (engineering, marketing, specialized, academic), with each agent described in a markdown file. The repository emphasizes clear documentation, consistent file organization, and automation via shell scripts.

You will learn:
- How to add or update agent documentation
- How to maintain division rosters in the README
- How to keep strategy and automation scripts up to date
- The coding conventions and commit patterns used in this project

---

## Coding Conventions

**File Naming**
- Use kebab-case for all files.
  - Example: `engineering/engineering-frontend.md`, `scripts/convert.sh`

**Import Style**
- Use relative imports in TypeScript files.
  - Example:
    ```typescript
    import { Agent } from '../types/agent';
    ```

**Export Style**
- Use named exports.
  - Example:
    ```typescript
    export function createAgent() { ... }
    ```

**Commit Messages**
- Prefix with `feat`, `fix`, or `docs` as appropriate.
- Use descriptive messages (~57 characters on average).
  - Example: `feat: add academic-researcher agent to academic division`

---

## Workflows

### Add New Agent
**Trigger:** When introducing a new agent role  
**Command:** `/add-agent`

1. Create a new markdown file in the appropriate division folder (`engineering/`, `marketing/`, `specialized/`, `academic/`).
2. Name the file using the pattern: `division/division-agent-name.md` (e.g., `engineering/engineering-frontend.md`).
3. Fill in agent details using the standard template.
   - Example:
     ```markdown
     ---
     name: Frontend Engineer
     description: Builds and maintains UI components.
     skills: [React, TypeScript, CSS]
     ---
     ```
4. Optionally, update `README.md` to add the new agent to the relevant division table.
5. Commit your changes with a descriptive message.

---

### Fix or Update Existing Agent
**Trigger:** When correcting or expanding an agent's documentation  
**Command:** `/update-agent`

1. Locate the agent's markdown file in its division folder.
2. Edit the file to correct errors, expand sections, or update formatting/frontmatter.
3. Optionally, mention the update in your commit message for traceability.
4. Commit your changes.

---

### Update README Division Roster or Tables
**Trigger:** When updating the main README to reflect agent roster changes  
**Command:** `/update-readme`

1. Edit `README.md` to add new agents to division tables, reorder sections, or fix formatting issues.
2. Ensure new agents are correctly listed under their division.
3. Commit the changes with a descriptive message.

---

### Rename or Fix Agent References in Strategy Docs
**Trigger:** When fixing outdated or incorrect agent references in strategy docs  
**Command:** `/fix-strategy-references`

1. Identify incorrect agent references in `strategy/*.md` or `strategy/playbooks/*.md`.
2. Edit the relevant files to update agent names for consistency.
   - Example:
     ```diff
     - The "Frontend Dev" agent handles UI.
     + The "Frontend Engineer" agent handles UI.
     ```
3. Commit the changes with a message referencing the fix.

---

### Add or Update Scripts for Automation
**Trigger:** When automating or improving agent processing  
**Command:** `/update-scripts`

1. Edit or create shell scripts in the `scripts/` directory (e.g., `convert.sh`, `install.sh`).
2. Update scripts to support new directories or improve automation (e.g., parallel execution, new division support).
   - Example:
     ```bash
     # scripts/convert.sh
     for dir in engineering marketing specialized academic; do
       ./convert-agents "$dir"
     done
     ```
3. Commit your changes with a descriptive message.

---

## Testing Patterns

- Test files follow the pattern: `*.test.*`
- The testing framework is not specified in the repository.
- Place test files alongside the code they test, using kebab-case naming.

  Example:
  ```
  src/
    agent.ts
    agent.test.ts
  ```

---

## Commands

| Command                | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| /add-agent             | Add a new agent to a division                                |
| /update-agent          | Fix or update an existing agent's documentation              |
| /update-readme         | Update the README division tables or roster                  |
| /fix-strategy-references | Fix agent references in strategy or playbook documentation |
| /update-scripts        | Add or update automation scripts in the scripts/ directory   |
```
