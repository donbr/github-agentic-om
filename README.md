# The GitHub-Native Agentic Operating Model

A comprehensive framework for managing blended human-AI engineering teams using GitHub as the unified coordination and governance plane.

## Why This Matters

The transition to AI-augmented software engineering demands more than tools—it requires **structure, governance, and process**. The prevailing ad-hoc approach creates technical debt, brittle code, and misalignment between intent and implementation. Organizations need a repeatable, auditable system that aligns both human and AI contributors on *what* to build and *why* before code is written.

This operating model provides that system.

> **GitHub is the control plane.**
> All contributors—human and AI—operate inside the same workflow, governed by the same rules, with complete auditability and traceability.

## Eight Governing Principles

This operating model is founded on eight core principles that serve as the constitutional basis for all technical and procedural decisions:

1. **Every contribution is a Pull Request** - No privilege escalation, no bypass routes
2. **Governance must be inside the SDLC** - GitHub RBAC, branch protections, and PR review form the safety perimeter
3. **Specification is the contract** - All work must begin with an approved spec and plan
4. **Ambiguity requires human judgment** - AI agents act autonomously only under low ambiguity and low risk
5. **Agents must be modular, audited, and version-controlled** - Their primitives, instructions, and MCP capabilities must be in source control
6. **CI/CD is a decision engine** - `Build → Measure → Analyze → Decide` is the backbone of engineering intelligence
7. **Documentation must live in the repository** - PR-driven doc updates prevent drift and improve discoverability
8. **Knowledge must be explicit** - ADRs preserve the *why* behind the *what*

## 🚀 Getting Started

This repository provides both **theory** (the complete operating model) and **practice** (phased adoption guides).

### For Implementation Teams

Start with the adoption materials for a practical, phased rollout:

1. **📋 [Adoption Playbook](docs/adoption-playbook.md)** - Phased implementation guide (Phase 0-4)
   - Phase 0: Preparation (Humans Only)
   - Phase 1: Human-Only Adoption (establish workflow and guardrails)
   - Phase 2: AI-Assisted Work (AI as helper, not author)
   - Phase 3: AI as Authorized Contributor (controlled autonomy)
   - Phase 4: Optimization & Automation (mature hybrid workflows)

2. **📊 [Adoption Slides](docs/adoption-slides.md)** - Executive summary deck for stakeholders

3. **🗺️ [Adoption Overview Diagram](docs/adoption-overview-diagram.md)** - Visual roadmap

### For Deep Understanding

Explore the complete framework and technical foundation:

- **[GitHub-Native Operating Model](docs/github-native-operating-model.md)** (600+ lines, 13 parts)
  - Complete whitepaper covering organizational model, strategic planning, specification layer, agentic execution, CI/CD as BMAD loop, and knowledge architecture

- **[Branching & Workflow Standard](docs/branching-workflow-standard.md)**
  - Tool-agnostic workflow foundation (trunk-based, PR-first, November 2025 current practices)

- **[Cursor Ruleset Implementation](docs/tooling/cursor-ruleset-v1.md)**
  - How Cursor rules enforce the workflow

## Core Artifacts

### Documentation
- **`docs/github-native-operating-model.md`** - Complete operating model (13 parts)
- **`docs/adoption-playbook.md`** - Phased implementation guide
- **`docs/adoption-slides.md`** - Executive presentation deck
- **`docs/adoption-overview-diagram.md`** - Visual adoption journey
- **`docs/branching-workflow-standard.md`** - Canonical workflow model

### Reference Configurations

This repository includes ready-to-use enforcement patterns:

**Cursor Enforcement Rules** (`dot-cursor/rules/`)
- `001-core-trunk-pr-first.mdc` - PR-first workflow enforcement
- `010-core-main-protection.mdc` - Main branch protection
- `200-repo-branching-workflow.mdc` - Branching standards
- `300-agentic-ai-rule.mdc` - AI agent behavior rules

**GitHub Templates** (`dot-github/`)
- `pull-request-template.md` - Structured PR format
- `branch-protection-example.md` - Branch protection settings

**AI Agent Instructions**
- `CLAUDE.md` - Behavioral contract for AI contributors

**Note:** The `dot-cursor/` and `dot-github/` directories use a `dot-` prefix to prevent automatic application. To activate:
1. Review the configurations in these directories
2. Copy/rename to `.cursor/` and `.github/` respectively
3. Customize for your organization's needs

## Key Architectural Patterns

- **Blended Teams**: 5 team types (org.owners, human.seniors, human.engineers, ai.developers, ai.evaluators)
- **RBAC Matrix**: Strict role-based access control preventing AI agents from Admin/Owner roles
- **Risk & Ambiguity Routing**: Matrix for determining human-in-the-loop checkpoints
- **Spec-Driven Development**: GitHub Spec Kit workflow (constitution → spec → plan → tasks → implement)
- **Git Worktrees**: Parallel, isolated workspaces for multi-agent development
- **BMAD Loop**: CI/CD as intelligence engine (Build → Measure → Analyze → Decide)

## Repository Structure

```
.
├── docs/
│   ├── github-native-operating-model.md    # Primary whitepaper (13 parts)
│   ├── adoption-playbook.md                # Phased implementation guide
│   ├── adoption-slides.md                  # Executive presentation
│   ├── adoption-overview-diagram.md        # Visual roadmap
│   ├── branching-workflow-standard.md      # Workflow foundation
│   └── tooling/
│       └── cursor-ruleset-v1.md            # Cursor implementation
├── dot-cursor/                              # Reference Cursor rules
│   └── rules/*.mdc
├── dot-github/                              # Reference GitHub templates
├── CLAUDE.md                                # AI agent instructions
├── CONTRIBUTING.md                          # Human contributor guide
├── LICENSE                                  # MIT License
└── README.md                                # This file
```

## Design Philosophy

This operating model is built on three core beliefs:

1. **AI agents can materially improve quality and velocity** - but only within a strong governance framework

2. **GitHub already provides the necessary primitives** - We don't need new platforms, just disciplined usage of branches, issues, projects, rules, CI, and reviews

3. **Governance should be embedded in the SDLC** - Not implemented as after-the-fact audits or external systems

## Intended Audience

This operating model is designed for:

- **AI-enabled engineering organizations** adopting agentic development
- **Hybrid human + AI development teams** seeking structure and safety
- **Enterprise platform teams** establishing governance for AI contributors
- **Engineering leaders** rolling out repository-level governance
- **ML/AI groups** standing up agent capabilities in production
- **Organizations** transitioning from ad-hoc AI usage to systematic integration

## What AI Agents Can Do

Within this model, AI agents are empowered to:

- Implement features from specifications
- Create branches using standard naming patterns
- Write and update tests
- Refactor code for consistency
- Propose documentation changes
- Open Pull Requests with structured templates
- Follow the Spec Kit workflow
- Operate in isolated git worktrees

**AI agents cannot:**

- Merge into protected branches
- Hold Admin or Owner roles
- Bypass PR requirements
- Self-approve changes
- Modify governance files without human review

This is **delegation with guardrails**, not unrestricted automation.

## Development Workflow

This repository practices what it preaches - it follows the trunk-based, PR-first workflow documented in the whitepaper.

- **`main` is protected** - all changes via Pull Requests
- **Branch naming**: `feature/<id>-<desc>`, `bugfix/<issue>-<fix>`, `refactor/<area>`, `docs/<topic>`
- **PR structure**: Summary, Context, Implementation Details, Testing, Risks & Rollback
- **AI agent behavior**: Governed by CLAUDE.md and Cursor rules

## For AI Agents

If you are an AI agent working in this repository:

- Follow the instructions in [CLAUDE.md](CLAUDE.md)
- Adhere to the eight governing principles
- Work only on short-lived branches
- Never commit directly to `main`
- Use the PR structure for all contributions
- Include reasoning and validation steps in PRs

## Version

**v2.0.0** - Comprehensive GitHub-Native Agentic Operating Model

Previous version (v1.2.0) focused narrowly on branching workflow. This version presents the complete operating model framework with phased adoption guidance.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

- **[CONTRIBUTING.md](CONTRIBUTING.md)** - Comprehensive guide for human contributors (editing conventions, PR process, development setup)
- **[CLAUDE.md](CLAUDE.md)** - AI agent guidance and behavioral rules

All contributions must follow the PR-first workflow and align with the eight governing principles.
