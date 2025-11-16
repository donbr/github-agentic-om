# Implement a feature following Spec-Driven Development

You will be implementing a new feature following the Spec-Driven Development workflow defined in the GitHub-Native Operating Model.

Feature to implement:

$ARGUMENTS

---

## IMPORTANT: Spec-Driven Development Workflow

This command enforces **Part VI (Specification Layer)** of the operating model:
- Constitution → Spec → Plan → Tasks → Implementation

Reference: @docs/github-native-operating-model.md#part-vi--specification-layer-spec-kit--constitution

---

## Pre-Implementation Checklist

Before writing ANY code, verify:

1. [ ] **Constitution exists**
   - Check for `@docs/specs/constitution.md` or `constitution.md` in project root
   - Constitution defines governing principles, tech stack, and testing standards
   - If missing, STOP and ask human to create it first

2. [ ] **Feature spec exists**
   - Check for spec file in `@docs/specs/` matching this feature
   - Spec defines the "what" and "why" of the feature
   - If missing, STOP and ask human to create spec.md first

3. [ ] **Plan has been approved**
   - Check for `plan.md` in the spec directory
   - Plan defines the "how" - implementation approach
   - If missing, offer to generate plan.md for human review
   - **MANDATORY**: Plan must be reviewed by human before implementation

4. [ ] **Human has approved the plan**
   - Ask: "Has the plan in plan.md been reviewed and approved?"
   - Do NOT proceed without explicit human approval
   - This implements Principle #4: Ambiguity requires human judgment

---

## Implementation Workflow

### Step 1: Review Context

Read the following files for context:

1. `@docs/specs/constitution.md` - Governing principles
2. `@docs/specs/<feature-name>/spec.md` - Feature specification
3. `@docs/specs/<feature-name>/plan.md` - Approved implementation plan

Summarize your understanding before proceeding.

### Step 2: Create or Update Tasks

If `tasks.md` doesn't exist:
- Create `@docs/specs/<feature-name>/tasks.md`
- Break down `plan.md` into granular, checkable tasks
- Each task should be independently testable
- Use checklist format:
  ```markdown
  - [ ] Task 1: Implement X
  - [ ] Task 2: Test X
  - [ ] Task 3: Document X
  ```

If `tasks.md` exists:
- Review remaining uncompleted tasks
- Continue from where previous implementation stopped

### Step 3: Implement Incrementally

For each task in `tasks.md`:

1. **Implement the task**
   - Follow the approved plan exactly
   - Do NOT deviate without human consultation
   - Keep changes focused and minimal

2. **Write tests**
   - Unit tests for new functions
   - Integration tests for module interactions
   - Aim for 90%+ code coverage

3. **Run tests**
   - Verify new tests pass
   - Verify existing tests still pass
   - If any test fails, fix immediately

4. **Update documentation**
   - Update `@docs/api/` if API changed
   - Update code comments
   - Update examples if behavior changed

5. **Check off task**
   - Mark task as complete in `tasks.md`
   - Commit changes with descriptive message
   - Use imperative mood: "Add X", not "Added X"

6. **Repeat for next task**

### Step 4: Final Validation

After all tasks complete:

1. **Run full test suite**
   ```bash
   # Example - adapt to your project
   pytest --cov=src tests/
   ```

2. **Verify documentation updated**
   - All code examples work
   - All links resolve
   - API docs reflect changes

3. **Review against spec**
   - Implementation matches spec requirements
   - No scope creep
   - All acceptance criteria met

4. **Prepare for PR**
   - All changes committed
   - Branch pushed to remote
   - Ready for Pull Request

---

## Constraints

### DO:
- ✅ Follow the approved plan exactly
- ✅ Write tests for all new code
- ✅ Update documentation alongside code
- ✅ Keep commits small and focused
- ✅ Run tests after each change
- ✅ Ask for clarification if plan is ambiguous

### DO NOT:
- ❌ Deviate from approved plan without human consultation
- ❌ Skip writing tests
- ❌ Skip updating documentation
- ❌ Make architectural decisions without approval
- ❌ Implement features not in the spec
- ❌ Commit directly to `main` branch

---

## Branch Workflow

Ensure you're working on a feature branch:

```bash
# If on main, create feature branch
git switch -c feature/<id>-<short-description>

# Example
git switch -c feature/123-user-profile-api
```

Reference: @docs/branching-workflow-standard.md

---

## Testing Requirements

**Minimum requirements:**
- Unit tests for all new functions
- Integration tests for module interactions
- 90%+ code coverage
- All existing tests must still pass

**Test-Driven Development preferred:**
1. Write failing test
2. Implement minimum code to pass
3. Refactor for clarity
4. Repeat

Reference: @docs/tooling/testing-with-claude-code.md

---

## Documentation Requirements

**Must update:**
- API documentation (`@docs/api/`)
- Code comments (docstrings, inline)
- Examples (if behavior changed)
- CHANGELOG.md (if exists)

**Check:**
- All code examples execute correctly
- All internal links resolve
- Mermaid diagrams compile

Reference: @docs/github-native-operating-model.md#part-ix--knowledge-architecture

---

## Pull Request Preparation

After implementation complete, use:

```
/create-pr <feature-name>
```

Or manually create PR with this structure:

```markdown
## Summary
- <1-3 bullets describing what was implemented>

## Context
- Implements spec: @docs/specs/<feature-name>/spec.md
- Follows plan: @docs/specs/<feature-name>/plan.md
- Plan-SHA: <commit hash of approved plan>

## Implementation Details
- <key design choices made>
- <any deviations from plan (with justification)>

## Testing
- <tests added>
- <coverage: X%>
- <how to validate manually>

## Risks & Rollback
- <potential impact>
- <how to revert: git revert <commit-sha>>
```

Reference: @CLAUDE.md#pull-request-structure

---

## Extended Thinking Mode

This command uses **"think" mode** for architectural work.

Reasons:
- Spec-driven implementation requires careful planning
- Need to align code with approved plan
- Must consider testing strategy
- Documentation updates require thoughtfulness

**Think mode allocates more reasoning budget for quality implementation.**

Think.
