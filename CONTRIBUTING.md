# Contributing to the GitHub-Native Agentic Operating Model

Thank you for your interest in contributing! This guide provides detailed information for human contributors working on this repository.

## Table of Contents

- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Editing the Operating Model Document](#editing-the-operating-model-document)
- [Working with Adoption Materials](#working-with-adoption-materials)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Code of Conduct](#code-of-conduct)

## Getting Started

### Prerequisites

- Git installed and configured
- Markdown editor (VS Code, Cursor, or similar)
- Basic familiarity with GitHub workflows
- Understanding of the eight governing principles (see README.md)

### First Steps

1. **Read the core documents**:
   - `README.md` - Overview and getting started
   - `docs/github-native-operating-model.md` - Complete framework
   - `docs/branching-workflow-standard.md` - Workflow foundation

2. **Review the reference configurations**:
   - `dot-cursor/rules/*.mdc` - Cursor enforcement rules
   - `dot-github/pull-request-template.md` - PR template

## Development Workflow

### Branch Protection

- `main` is protected - all changes must go through Pull Requests
- Treat `main` as the always-deployable trunk
- Never commit directly to `main`

### Branch Naming Conventions

Use these patterns (from `docs/branching-workflow-standard.md`):

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

### Commit Guidelines

- Keep commits small and focused
- Use imperative commit messages ("Add feature" not "Added feature")
- Reference issues when applicable (#123)
- Delete branches after merge

## Editing the Operating Model Document

### File: `docs/github-native-operating-model.md`

This 600+ line whitepaper is the core artifact. When editing:

#### Structure Preservation

1. **Maintain the 13-part organization**:
   - Part I-III: Executive overview and guiding principles
   - Part IV: Organizational Operating Model
   - Part V: Strategic Planning Layer
   - Part VI: Specification Layer
   - Part VII: Agentic Execution Layer
   - Part VIII: CI/CD as BMAD Loop
   - Part IX: Knowledge Architecture
   - Part X: End-to-End Playbooks
   - Part XI: Governance Appendix
   - Part XII-XIII: Conclusion and references

2. **Preserve hierarchical numbering**: Use consistent heading levels (##, ###, ####)

3. **Keep section flow**: Maintain the progression: governance → planning → specification → execution → measurement → knowledge

#### Citation Management

References in Part XIII use a specific format:

```markdown
1. Title of Document, accessed November 13, 2025, [URL](URL)
```

**Rules**:
- Numbered list items (currently 1-59)
- Include title, access date, and URL
- Sources include GitHub Docs, GitHub Blog, academic papers, and industry resources
- Add new references in sequential order at the end
- Update references in the text using superscript numbers (¹, ², ³)

#### Mermaid Diagrams

The whitepaper contains several Mermaid diagrams:

- **Part III**: Layered architecture flowchart
- **Part VI**: Specification sequence diagram
- **Part VIII**: BMAD loop graph
- **Part IX**: Knowledge architecture graph

**When modifying diagrams**:
1. Ensure they align with the narrative content
2. Use consistent node naming conventions
3. Test rendering in your editor before committing
4. Maintain the "Code snippet" block format
5. Keep colors and styling consistent with existing diagrams

#### Terminology Consistency

Always use established terms:
- **BMAD** (not "BMAD Loop" in some places and "Build-Measure-Analyze-Decide" in others)
- **RBAC Matrix** (not "role-based access control matrix")
- **MCP Registry** (not "Model Context Protocol registry")
- **Spec Kit** (not "GitHub Spec Kit" unless specifically referring to the GitHub tool)
- **Git Worktrees** (not "git worktree" or "worktrees")

#### Content Coherence

The whitepaper follows a layered architecture metaphor:

- **Layer 1 (Foundation)**: Organizational governance
- **Layer 2 (Planning)**: Strategic work intake
- **Layer 3 (Specification)**: Human intent → machine-readable specs
- **Layer 4 (Execution)**: Agentic implementation
- **Layer 5 (Intelligence)**: CI/CD feedback loop
- **Layer 6 (Knowledge)**: Documentation and ADRs

Ensure all sections maintain consistency with this architectural stack.

#### Principle Alignment

All recommendations must align with the eight governing principles:

1. Every contribution is a Pull Request
2. Governance must be inside the SDLC
3. Specification is the contract
4. Ambiguity requires human judgment
5. Agents must be modular, audited, and version-controlled
6. CI/CD is a decision engine
7. Documentation must live in the repository
8. Knowledge must be explicit

## Working with Adoption Materials

Files: `docs/adoption-playbook.md`, `docs/adoption-slides.md`, `docs/adoption-overview-diagram.md`

### Guidelines

1. **Maintain consistency** across the three formats (playbook, slides, diagram)
2. **Preserve the phased structure**: Phase 0 (Preparation) → Phase 4 (Optimization & Automation)
3. **Align with the operating model**: All adoption guidance must reflect the eight governing principles
4. **Reference existing patterns**: Link to whitepaper sections rather than duplicating content
5. **Keep adoption materials high-level**: These are roadmaps, not detailed implementation guides

### Recent Structure

The adoption playbook includes:
- **Phase 0**: Explicit reference to the Eight Governing Principles
- **Phase 3**: Complete branch naming patterns with explanations
- **Phase 3**: Git Worktrees section explaining parallel agent development infrastructure

## Pull Request Guidelines

### PR Structure

Use this template (enforced by `dot-github/pull-request-template.md`):

```markdown
## Summary
- <1-3 bullets describing what changed>

## Context
- <why this change exists>
- <what problem it solves>

## Implementation Details
- <design choices>
- <technical approach>

## Testing
- <validation steps>
- <how to verify the changes>

## Risks & Rollback
- <potential impact>
- <how to revert if needed>
```

### Review Process

1. **Self-review**: Read through your changes before requesting review
2. **Documentation**: Update relevant docs if you change functionality
3. **Testing**: Verify your changes don't break existing content
4. **Alignment**: Ensure changes align with the eight governing principles

### For AI-Assisted Contributions

If you used AI assistance in creating your PR:
- Mention it in the PR description
- Review all AI-generated content carefully
- Ensure accuracy of citations and references
- Verify terminology consistency

## Code of Conduct

### Expected Behavior

- Be respectful and inclusive
- Focus on constructive feedback
- Maintain professional communication
- Follow the PR-first workflow

### Prohibited Actions

- Committing directly to `main`
- Bypassing PR requirements
- Making sweeping changes without discussion
- Modifying governance files without team consensus

## Questions?

- Open an issue for questions about contributing
- Reference `CLAUDE.md` for AI agent-specific guidance
- See `README.md` for project overview and structure

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
