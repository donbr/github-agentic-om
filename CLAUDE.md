# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository documents "The GitHub-Native Agentic Operating Model" - a framework for managing blended human-AI engineering teams using GitHub as the unified coordination and governance plane.

### Primary Artifacts

- **@docs/github-native-operating-model.md** - Complete 13-part framework (600+ lines)
- **@docs/adoption-playbook.md** - Phased implementation guide (Phase 0-4)
- **@docs/adoption-slides.md** - Executive presentation deck
- **@docs/adoption-overview-diagram.md** - Visual adoption roadmap
- **@docs/branching-workflow-standard.md** - Canonical workflow (November 2025 practices)

### License and Version

- **License**: MIT License - Open source, freely available for commercial and non-commercial use
- **Version**: v2.0.0 - Comprehensive operating model with phased adoption guidance
- **README Structure**: Features "Getting Started" section separating implementation guidance (adoption materials) from deep understanding (operating model)

## Development Workflow

This repository practices what it preaches - it follows the trunk-based, PR-first workflow documented in the whitepaper.

### Branch Protection

- **`main` is protected** - treat it as the always-deployable trunk
- **Never commit directly to `main`** - all changes must go through Pull Requests
- **Create short-lived feature branches** for all non-trivial work

### Branch Naming

Use these conventions from @docs/branching-workflow-standard.md:

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

### Working on Main Branch

If you detect the current branch is `main`:
- **Avoid making edits** unless the change is trivial AND user explicitly insists
- For non-trivial work, guide user to create a feature branch first:
  ```
  git checkout -b feature/<short-tag>-<description>
  ```
- Before any commit, encourage inspection commands:
  - `git status` - See what's staged
  - `git diff` - Review changes
  - `git log --oneline` - Check recent commits

### Git Safety

- **Never suggest force pushes** unless explicitly requested by user
- Encourage reviewing changes before committing
- Verify changes align with PR scope

## AI Agent Behavior

As an AI contributor to this repository, you must follow the Development Workflow above. Additionally:

### Prohibited Actions

- Never commit directly to `main`
- Never bypass PR requirements
- Never make sweeping multi-file changes without explicit user request
- Never suggest force pushes unless explicitly requested by user
- If current branch is `main`, avoid making edits (create feature branch instead)

### Required in Pull Requests

- Use the PR structure template shown above
- Include reasoning summary in Context section
- Include implementation details
- Include validation steps in Testing section
- Include risk assessment in Risks & Rollback section
- **Explain which files will change and why**
- **Suggest how to validate the changes**

### Code Change Constraints

When implementing changes:
- **Keep diffs small** - Avoid large, sweeping modifications
- **Prefer incremental PRs** - Multiple small PRs are better than one large PR
- **Avoid structural rewrites** unless explicitly requested by user
- **Recommend appropriate tests** - Propose tests aligned with the changes
- **Ensure alignment** with trunk-based workflow and the eight governing principles

This repository is itself a demonstration of the GitHub-Native Agentic Operating Model it documents.

## Key Patterns to Understand

### Eight Governing Principles

The operating model is founded on eight core principles (see Part II of @docs/github-native-operating-model.md or README.md):

1. Every contribution is a Pull Request
2. Governance must be inside the SDLC
3. Specification is the contract
4. Ambiguity requires human judgment
5. Agents must be modular, audited, and version-controlled
6. CI/CD is a decision engine
7. Documentation must live in the repository
8. Knowledge must be explicit

### Git Worktrees

**Critical for multi-agent development**: Git worktrees enable parallel agent work in isolated workspaces, preventing context confusion when multiple agents work simultaneously. Each agent operates in its own worktree without conflicts. See Part VII of the operating model for implementation details.

### Spec-Driven Development

All work follows the GitHub Spec Kit workflow: Constitution → Spec → Plan → Tasks → Implementation. See Part VI for details.

### Risk & Ambiguity Routing

The operating model includes a matrix for determining human-in-the-loop checkpoints based on risk and ambiguity levels. See Part VI for the routing matrix.

## Editing the Operating Model

When editing @docs/github-native-operating-model.md:

### Critical Rules

1. **Preserve Structure**: Maintain the 13-part organization (Parts I-XIII) and hierarchical numbering
2. **Maintain References**: All citations use superscript numbers (¹, ²) linking to Part XIII
3. **Consistent Terminology**: Use established terms (BMAD, RBAC Matrix, MCP Registry, Spec Kit, Git Worktrees)
4. **Principle Alignment**: Ensure all recommendations align with the eight governing principles

### Detailed Guidelines

See CONTRIBUTING.md for:
- Complete 13-part structure breakdown
- Citation format specifications
- Mermaid diagram guidelines
- Content coherence requirements
- Terminology reference

## Working with Adoption Materials

When working on @docs/adoption-*.md files:

1. **Maintain consistency** across the three formats (playbook, slides, diagram)
2. **Preserve the phased structure**: Phase 0 (Preparation) → Phase 4 (Optimization & Automation)
3. **Align with the operating model**: All adoption guidance must reflect the eight governing principles
4. **Reference existing patterns**: Link to whitepaper sections rather than duplicating content
5. **Keep adoption materials high-level**: These are roadmaps, not detailed implementation guides

### Recent Enhancements to Adoption Playbook

The adoption playbook now includes:
- **Phase 0**: Explicit reference to the Eight Governing Principles
- **Phase 3**: Complete branch naming patterns (feature, bugfix, refactor, docs) with explanations
- **Phase 3**: Git Worktrees section explaining parallel agent development infrastructure

## Reference Configurations

The repository includes enforcement patterns in:
- `dot-cursor/rules/*.mdc` - Cursor enforcement rules
- `dot-github/` - GitHub templates (PR template, branch protection examples)
- `.mcp.json` - MCP server configuration (time, sequential-thinking, Context7, ai-docs-server)

Note: `dot-cursor/` and `dot-github/` use `dot-` prefix to prevent automatic application. Review and rename to `.cursor/` and `.github/` to activate.

## For Human Contributors

See CONTRIBUTING.md for:
- Development environment setup
- Detailed editing conventions
- Pull request process
- Citation management
- Mermaid diagram guidelines
- Code of conduct
