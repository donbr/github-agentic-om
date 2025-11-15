# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains a comprehensive whitepaper documenting "The GitHub-Native Agentic Operating Model" - a framework for managing blended human-AI engineering teams using GitHub as the unified coordination and governance plane.

The primary artifact is `github-native-operating-model.md`, which defines an operating model grounded in eight core principles for AI-augmented software engineering organizations.

## Development Workflow

This repository practices what it preaches - it follows the trunk-based, PR-first workflow documented in the whitepaper.

### Branch Protection

- **`main` is protected** - treat it as the always-deployable trunk
- **Never commit directly to `main`** - all changes must go through Pull Requests
- **Create short-lived feature branches** for all non-trivial work

### Branch Naming

Use these conventions (from `docs/branching-workflow-standard.md`):

```
feature/<id>-<short-description>
bugfix/<issue-id>-<fix>
refactor/<area>
docs/<topic>
```

Examples:
```
feature/143-add-neo4j-gds-loader
bugfix/77-fix-ragas-metric
docs/update-contribution-guide
```

### Pull Request Structure

When creating PRs, use this format (enforced by `dot-cursor/rules/001-core-trunk-pr-first.mdc`):

```markdown
## Summary
- <1-3 bullets>

## Context
- <why this exists>

## Implementation Details
- <design choices>

## Testing
- <validation steps>

## Risks & Rollback
- <revert plan>
```

### Commits

- Keep commits small and focused
- Use imperative commit messages
- Delete branches after merge

## Architecture Overview

### Document Structure

The whitepaper is organized into 13 parts:

1. **Part I-III**: Executive overview and guiding principles
2. **Part IV**: Organizational Operating Model - GitHub org structure, RBAC matrix, and MCP registry
3. **Part V**: Strategic Planning Layer - GitHub Projects as Program Board
4. **Part VI**: Specification Layer - Spec Kit workflow (constitution, specs, plans, tasks)
5. **Part VII**: Agentic Execution Layer - Agent roles, git worktrees, and PR workflows
6. **Part VIII**: CI/CD as BMAD Loop (Build-Measure-Analyze-Decide)
7. **Part IX**: Knowledge Architecture - Documentation structure and ADRs
8. **Part X**: End-to-End Playbooks
9. **Part XI**: Governance Appendix
10. **Part XII-XIII**: Conclusion and references

### Core Concepts

**Eight Governing Principles:**
1. Every contribution is a Pull Request
2. Governance must be inside the SDLC
3. Specification is the contract
4. Ambiguity requires human judgment
5. Agents must be modular, audited, and version-controlled
6. CI/CD is a decision engine
7. Documentation must live in the repository
8. Knowledge must be explicit

**Key Architectural Patterns:**
- **Blended Teams**: Five team types (org.owners, human.seniors, human.engineers, ai.developers, ai.evaluators)
- **RBAC Matrix**: Strict role-based access control preventing AI agents from having Admin/Owner roles
- **Risk & Ambiguity Routing**: Matrix for determining human-in-the-loop checkpoints
- **Spec-Driven Development**: Using GitHub Spec Kit (/specify, /plan, /tasks, /implement)
- **Git Worktrees**: Parallel, isolated workspaces for multi-agent development
- **BMAD Loop**: CI/CD as an intelligence engine (Build → Measure → Analyze → Decide)

## Working with This Repository

### Document Editing Guidelines

When editing `github-native-operating-model.md`:

1. **Preserve Structure**: Maintain the 13-part organization and hierarchical numbering
2. **Maintain References**: All citations use superscript numbers (e.g., ¹, ²) linking to Part XIII
3. **Code Blocks**: Mermaid diagrams are embedded as "Code snippet" blocks
4. **Consistent Terminology**: Use established terms (BMAD, RBAC, MCP Registry, Spec Kit, etc.)
5. **Principle Alignment**: Ensure all recommendations align with the eight core principles

### Key Files

- `github-native-operating-model.md`: The complete whitepaper (500+ lines)
- `docs/branching-workflow-standard.md`: Canonical branching and workflow model (tool-agnostic)
- `docs/tooling/cursor-ruleset-v1.md`: How Cursor rules enforce the workflow
- `dot-cursor/rules/*.mdc`: Cursor enforcement rules (trunk-based PR-first workflow)
- `dot-github/`: GitHub templates (PR template, branch protection examples)
- `.mcp.json`: MCP server configuration (includes ai-docs-server for documentation fetching)

### Content Coherence

The whitepaper follows a layered architecture metaphor:
- Layer 1 (Foundation): Organizational governance
- Layer 2 (Planning): Strategic work intake
- Layer 3 (Specification): Human intent → machine-readable specs
- Layer 4 (Execution): Agentic implementation
- Layer 5 (Intelligence): CI/CD feedback loop
- Layer 6 (Knowledge): Documentation and ADRs

All sections should maintain consistency with this architectural stack and the flow: governance → planning → specification → execution → measurement → knowledge.

### Citation Management

References in Part XIII use a specific format:
- Numbered list items (1-59)
- Title, access date, and URL
- Sources include GitHub Docs, GitHub Blog, academic papers, and industry resources

When adding new references, maintain this format and add them to Part XIII in sequential order.

### Mermaid Diagrams

The whitepaper contains several Mermaid diagrams:
- Part III: Layered architecture flowchart
- Part VI: Specification sequence diagram
- Part VIII: BMAD loop graph
- Part IX: Knowledge architecture graph

When modifying diagrams, ensure they align with the narrative content and use consistent node naming conventions.

## MCP Server Configuration

This repository uses several MCP servers defined in `.mcp.json`:
- `mcp-server-time`: Time/timezone utilities
- `sequential-thinking`: Sequential reasoning tool
- `Context7`: Library documentation fetcher
- `ai-docs-server` and `ai-docs-server-full`: Documentation access for MCP, LangChain, LangGraph, and Anthropic docs

These servers support research and documentation tasks related to the operating model.

## AI Agent Behavior

As an AI contributor to this repository, you must:

1. **Work only on short-lived branches** - never commit directly to `main`
2. **Use the PR structure above** when creating Pull Requests
3. **Include reasoning and validation steps** in all PRs
4. **Make small, incremental commits** - avoid multi-file sweeping rewrites unless explicitly requested
5. **Respect branch protection** - PRs are the human-in-the-loop safety checkpoint

This repository is itself a demonstration of the GitHub-Native Agentic Operating Model it documents.