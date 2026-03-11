# agency-agents Development Patterns

> Auto-generated skill from repository analysis

## Overview

The agency-agents repository is a TypeScript-based collection of AI agent definitions organized by categories/divisions. It provides a structured framework for managing and distributing agent prompts and configurations through markdown files with frontmatter metadata. The repository includes installation scripts, CI/CD workflows, and integration support for various external platforms.

## Coding Conventions

### File Naming
- Use **kebab-case** for all files: `agent-name.md`, `install-script.sh`
- Agent files follow pattern: `{category}/{agent-name}.md`
- Script files in `scripts/` directory use descriptive names

### Agent File Structure
```markdown
---
name: "Agent Name"
description: "Brief description"
category: "category-name"
tags: ["tag1", "tag2"]
---

# Agent Name

## Description
Detailed description of the agent's purpose and capabilities.

## Instructions
Step-by-step instructions or prompt content.

## Examples
Example usage or interactions.
```

### Import/Export Patterns
- Mixed import styles used throughout codebase
- Export styles vary by file type and purpose
- Scripts use standard bash conventions

### Commit Messages
- Use conventional commit prefixes: `fix:`, `feat:`
- Keep messages concise (average 59 characters)
- Use freeform descriptive text after prefix

## Workflows

### New Agent Addition
**Trigger:** When someone wants to create a new agent for a specific domain
**Command:** `/new-agent`

1. Create agent markdown file in appropriate category directory using kebab-case naming
2. Add proper frontmatter with name, description, category, and relevant tags
3. Structure content with clear sections: Description, Instructions, Examples
4. Update README.md to increment agent count or add category if new
5. Ensure agent follows standard format and content guidelines

### New Category Preparation
**Trigger:** When adding agents to a new category that needs script support
**Command:** `/new-category`

1. Add category to `.github/workflows/lint-agents.yml` in the matrix strategy
2. Add category to `scripts/convert.sh` AGENT_DIRS array
3. Update `scripts/install.sh` to handle the new category
4. Modify `scripts/lint-agents.sh` to include category validation
5. Test all scripts work with the new category structure

### Integration Addition
**Trigger:** When someone wants to add integration with a new external tool
**Command:** `/new-integration`

1. Create `integrations/{tool-name}/README.md` with integration documentation
2. Update main `README.md` to list the new integration in appropriate section
3. Modify `scripts/install.sh` to handle installation/setup for the integration
4. Add any generated files or directories to `.gitignore` if needed
5. Test integration works across different platforms

### Bulk Agent Enhancement
**Trigger:** When introducing new standardized fields across all agents
**Command:** `/bulk-enhance`

1. Update all agent markdown files with new frontmatter fields or content structure
2. Update `CONTRIBUTING.md` with documentation for new fields or requirements
3. Modify `README.md` if the changes affect repository description or usage
4. Update conversion scripts in `scripts/convert.sh` if needed for new fields
5. Ensure all agents maintain consistency after bulk changes

### Install Script Enhancement
**Trigger:** When adding new functionality to the installation process
**Command:** `/enhance-install`

1. Modify `scripts/install.sh` with new features or improvements
2. Add platform detection logic if supporting new operating systems
3. Include proper error handling and user feedback
4. Test installation process across different environments
5. Update documentation if installation process changes

### Single Agent Refinement
**Trigger:** When refining an agent based on feedback or requirements
**Command:** `/refine-agent`

1. Locate the specific agent markdown file to modify
2. Update content, examples, or frontmatter based on requirements
3. Ensure changes maintain consistency with other agents
4. Test agent content if applicable
5. Commit with descriptive message about specific improvements

## Testing Patterns

### Test File Structure
- Test files follow pattern: `*.test.*`
- Framework details not clearly defined in analysis
- Focus on functionality validation over unit testing

### Validation Approach
- Uses linting workflows for agent validation
- Script-based validation in `lint-agents.sh`
- CI/CD pipeline validates changes automatically

## Commands

| Command | Purpose |
|---------|---------|
| `/new-agent` | Create a new agent in appropriate category with proper structure |
| `/new-category` | Set up infrastructure for a new agent category |
| `/new-integration` | Add support for external tool/platform integration |
| `/bulk-enhance` | Apply standardized improvements across all agents |
| `/enhance-install` | Improve installation script functionality |
| `/refine-agent` | Make targeted improvements to specific agent |