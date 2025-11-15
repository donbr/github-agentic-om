# The GitHub-Native Agentic Operating Model

A comprehensive framework for managing blended human-AI engineering teams using GitHub as the unified coordination and governance plane.

## Overview

This repository documents an enterprise-ready operating model grounded in eight core principles for AI-augmented software engineering organizations. It transforms GitHub into a complete "factory floor" for governed, auditable, and scalable agentic development.

## Core Artifacts

### Primary Document
- **`docs/github-native-operating-model.md`** (600+ lines)
  The complete whitepaper organized into 13 parts covering:
  - Organizational operating model (GitHub teams, RBAC, MCP registry)
  - Strategic planning layer (GitHub Projects as Program Board)
  - Specification layer (Spec Kit workflow)
  - Agentic execution layer (agent roles, git worktrees, PR workflows)
  - CI/CD as BMAD Loop (Build-Measure-Analyze-Decide)
  - Knowledge architecture (documentation, ADRs)
  - End-to-end playbooks

### Supporting Documentation
- **`docs/branching-workflow-standard.md`**
  Tool-agnostic branching and workflow model (trunk-based, PR-first)

- **`docs/tooling/cursor-ruleset-v1.md`**
  How Cursor rules enforce the workflow (implementation guide)

## Eight Governing Principles

1. Every contribution is a Pull Request
2. Governance must be inside the SDLC
3. Specification is the contract
4. Ambiguity requires human judgment
5. Agents must be modular, audited, and version-controlled
6. CI/CD is a decision engine
7. Documentation must live in the repository
8. Knowledge must be explicit

## Reference Implementation

This repository includes reference configurations:

### Cursor Enforcement Rules (`dot-cursor/rules/`)
- `001-core-trunk-pr-first.mdc` - PR-first workflow enforcement
- `010-core-main-protection.mdc` - Main branch protection
- `200-repo-branching-workflow.mdc` - Branching standards
- `300-agentic-ai-rule.mdc` - AI agent behavior rules

### GitHub Templates (`dot-github/`)
- `pull-request-template.md` - Structured PR format
- `branch-protection-example.md` - Branch protection settings

**Note:** The `dot-cursor/` and `dot-github/` directories use a `dot-` prefix to prevent automatic application. To activate these rules:
1. Review the configurations in these directories
2. Copy/rename to `.cursor/` and `.github/` respectively
3. Customize for your organization's needs

## Key Architectural Patterns

- **Blended Teams**: 5 team types (org.owners, human.seniors, human.engineers, ai.developers, ai.evaluators)
- **RBAC Matrix**: Strict role-based access control preventing AI agents from Admin/Owner roles
- **Risk & Ambiguity Routing**: Matrix for human-in-the-loop checkpoints
- **Spec-Driven Development**: GitHub Spec Kit workflow (constitution → spec → plan → tasks → implement)
- **Git Worktrees**: Parallel, isolated workspaces for multi-agent development
- **BMAD Loop**: CI/CD as intelligence engine (Build → Measure → Analyze → Decide)

## Repository Structure

```
.
├── docs/
│   ├── github-native-operating-model.md    # Primary whitepaper
│   ├── branching-workflow-standard.md      # Workflow foundation
│   └── tooling/
│       └── cursor-ruleset-v1.md            # Cursor implementation
├── dot-cursor/                              # Reference Cursor rules
│   └── rules/*.mdc
├── dot-github/                              # Reference GitHub templates
├── CLAUDE.md                                # AI agent instructions
└── README.md                                # This file
```

## Usage

### For Organizations
1. Read [docs/github-native-operating-model.md](docs/github-native-operating-model.md) to understand the complete framework
2. Review [docs/branching-workflow-standard.md](docs/branching-workflow-standard.md) for workflow foundations
3. Adapt the reference configurations in `dot-cursor/` and `dot-github/` to your needs
4. Implement incrementally following the layered architecture

### For AI Agents
- Follow the instructions in [CLAUDE.md](CLAUDE.md)
- Adhere to the eight governing principles
- Work only on short-lived branches
- Use the PR structure for all contributions

## Development Workflow

This repository practices what it preaches - it follows the trunk-based, PR-first workflow documented in the whitepaper.

- **`main` is protected** - all changes via Pull Requests
- **Branch naming**: `feature/<id>-<desc>`, `bugfix/<issue>-<fix>`, `refactor/<area>`, `docs/<topic>`
- **PR structure**: Summary, Context, Implementation, Testing, Risks & Rollback

## Version

**v2.0.0** - Comprehensive GitHub-Native Agentic Operating Model

Previous version (v1.2.0) focused narrowly on branching workflow. This version presents the complete operating model framework.

## License

[Specify license]

## Contributing

See [CLAUDE.md](CLAUDE.md) for contribution guidelines and workflow instructions.
