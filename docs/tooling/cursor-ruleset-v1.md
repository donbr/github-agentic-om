# Cursor Ruleset v1.0.0 (Implementation of Branching Workflow)

This document describes how Cursor is configured to **enforce or assist** the branching workflow
defined in `docs/branching_workflow_standard.md`.

Cursor uses `.mdc` rule files under `.cursor/rules/` to influence LLM behavior.

## Goals

- Treat `main` as a protected trunk.
- Steer all meaningful work to short-lived branches.
- Ensure merges into `main` happen via Pull Requests.
- Encourage small, focused commits.
- Require AI agents to provide reasoning, validation steps, and risk awareness in PRs.

## Files

- `.cursor/rules/001-core-trunk-pr-first.mdc`  
  Global rule: trunk-based, PR-first workflow.

- `.cursor/rules/010-core-main-protection.mdc`  
  Global rule: treat `main` as protected; avoid direct edits.

- `.cursor/rules/200-repo-branching-workflow.mdc`  
  Repo-specific conventions (branch naming, PR expectations).

- `.cursor/rules/300-agentic-ai-rule.mdc`  
  Agentic behavior rules: AI contributors must work on branches and open PRs with reasoning.

## Usage

1. Place the `.cursor/rules/` directory in the root of your repository.
2. Open the project in Cursor.
3. Cursor will automatically load these rules and adjust suggestions accordingly:
   - If you’re on `main` and ask for changes, it will recommend creating a feature branch.
   - When preparing changes for review, it will suggest a structured PR description.
   - For AI-driven work, it will prefer small diffs and explicit validation steps.

The `.mdc` files themselves are the source of truth for enforcement behavior.
This document exists to explain how they relate back to the branching standard.
