# agency-agents Development Patterns

> Auto-generated skill from repository analysis

## Overview

The agency-agents repository is a comprehensive collection of AI agent specifications organized by category. It serves as a community-driven resource for AI agent prompts and configurations, with agents categorized into domains like business, engineering, marketing, and specialized markets. The codebase focuses on maintaining a well-organized collection of markdown files with proper documentation and tooling integrations for various AI platforms.

## Coding Conventions

### File Naming
- Use **kebab-case** for all files: `category-agent-name.md`
- Agent files follow pattern: `{category}/{category}-{agent-name}.md`
- Script files: `install.sh`, `convert.sh`

### Agent File Structure
```markdown
---
# YAML frontmatter for metadata
title: "Agent Name"
category: "category-name"
---

# Agent Description

[Agent prompt and instructions]
```

### Import/Export Style
- Mixed import styles accepted (relative and absolute paths)
- Mixed export patterns (default and named exports)

### Commit Messages
- Average length: ~59 characters
- Common prefixes: `fix:`, `feat:`
- Freeform style accepted
- Examples: `fix: trailing newline`, `feat: add china market agents`

## Workflows

### Add New Agent
**Trigger:** When someone wants to contribute a new agent specialization
**Command:** `/add-agent`

1. Create new markdown file in appropriate category directory
   ```bash
   touch {category}/{category}-{agent-name}.md
   ```
2. Add agent content with proper YAML frontmatter
3. Add agent entry to README.md division table under correct category
4. Update total agent count in README.md header
5. Fix any formatting/linting issues (trailing newlines, quotes)
6. Create pull request for review
7. Merge after maintainer approval

### Batch Agent Addition
**Trigger:** When adding multiple agents in a specific domain or market
**Command:** `/add-agent-batch`

1. Create multiple agent files in relevant categories
   ```bash
   # Example: Adding China market agents
   touch marketing/marketing-china-social-media.md
   touch business/business-china-ecommerce.md
   touch engineering/engineering-china-platforms.md
   ```
2. Batch update README.md with all new agent entries
3. Update total agent count to reflect all additions
4. Ensure consistent formatting across all new files
5. Create single comprehensive PR for the entire batch
6. Include descriptive commit message covering all additions

### Fix Agent Formatting
**Trigger:** When linting or validation catches formatting issues
**Command:** `/fix-formatting`

1. Identify specific formatting issue (trailing newlines, YAML frontmatter, quotes)
2. Apply fix to affected agent file(s)
   ```bash
   # Common fixes:
   # - Add trailing newline
   # - Fix YAML frontmatter syntax
   # - Standardize quote usage
   ```
3. Commit with descriptive message: `fix: {specific issue} in {agent-name}`
4. Push directly to main branch (for maintainers)

### Update Tooling Integration
**Trigger:** When adding support for a new AI tool or fixing existing integrations
**Command:** `/add-tool-support`

1. Update `scripts/install.sh` with new tool installation logic
2. Update `scripts/convert.sh` if format conversion needed
3. Add tool documentation section to main README.md
4. Update `.gitignore` with tool-specific ignore patterns
5. Create integration-specific README: `integrations/{tool}/README.md`
6. Test installation and conversion scripts
7. Commit changes with `feat: add {tool} integration`

### README Maintenance
**Trigger:** When README becomes out of sync with repository contents
**Command:** `/sync-readme`

1. Audit all category directories for missing agents in README
2. Add missing agents to appropriate division tables
3. Recount total agents and update header statistics
4. Update tool support documentation section
5. Fix any outdated links or information
6. Verify all agent links resolve correctly
7. Commit with `fix: sync README with current agents`

### Pull Request Merge
**Trigger:** When a community PR is ready for merge after review
**Command:** `/merge-pr`

1. Review PR for adherence to conventions
2. Check agent file formatting and structure
3. Verify README.md updates are included
4. Merge pull request via GitHub interface
5. Apply any post-merge formatting fixes if needed
6. Follow up with README sync if contributor missed updates
7. Monitor for any CI/linting failures post-merge

## Testing Patterns

- Test files follow pattern: `*.test.*`
- Testing framework not clearly established
- Primary validation appears to be:
  - Markdown formatting validation
  - YAML frontmatter syntax checking
  - Link verification
  - Agent count accuracy in README

## Commands

| Command | Purpose |
|---------|---------|
| `/add-agent` | Add a single new AI agent with proper categorization |
| `/add-agent-batch` | Add multiple related agents in a themed batch |
| `/fix-formatting` | Fix formatting issues in agent files |
| `/add-tool-support` | Add or update AI development tool integrations |
| `/sync-readme` | Update README to reflect current repository state |
| `/merge-pr` | Merge community contributions with proper cleanup |