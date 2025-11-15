Below are the **accompanying architecture diagrams** for your unified whitepaper.  
They are written in **Mermaid**, ready for GitHub, Notion, Obsidian, MkDocs, or GitHub Pages.

I’m giving you **four diagrams**, each capturing a different layer of the operating model:

1. **Layered Architecture Overview (Core Diagram)**
    
2. **Specification-to-Execution Flow (Spec Kit Pipeline)**
    
3. **Agentic Execution Lifecycle (Plan Mode → Agent Mode → PR)**
    
4. **BMAD CI/CD Loop (Build-Measure-Analyze-Decide)**
    

They are clean, enterprise-ready, and aligned with your whitepaper structure.

---

# 🔶 **1. Layered Architecture Overview (The Whole System in One Diagram)**

This is the centerpiece. It visually expresses the entire “GitHub-Native Agentic Organization.”

```mermaid
flowchart TB
    %% LAYER 1: ORG GOVERNANCE
    subgraph GOV["Part II — Organizational Layer<br/>(GitHub Org as Control Plane)"]
        TEAMS["GitHub Teams<br/>• team.org.owners<br/>• team.human.seniors<br/>• team.human.engineers<br/>• team.ai.developers<br/>• team.ai.evaluators"]
        RBAC["RBAC & Branch Protections<br/>• Human-only merge<br/>• Agent write-only<br/>• No admin privileges"]
        MCP["MCP Registry (Private)<br/>Human-approved tool allow list"]
        GHCR["ghcr.io<br/>Container Registry for Agents + Microservices"]
    end

    %% LAYER 2: STRATEGIC PLANNING
    subgraph PLAN["Part III — Strategic Planning Layer<br/>(SAFE-Inspired Program Board)"]
        PROJECTS["GitHub Projects (Org-Level PI Board)<br/>• Epics / Features / Stories / Tasks<br/>• Custom Fields (Assignee-Type, Risk, Iteration)"]
        INTAKE["Intake Automation<br/>Issues → Project Board"]
        DISPATCH["AI Dispatch Workflow<br/>Assign issues to agents based on rules"]
    end

    %% LAYER 3: SPECIFICATION
    subgraph SPEC["Part IV — Specification Layer<br/>(Spec-Driven Development)"]
        SPECIFY["/specify → spec.md"]
        PLANMD["/plan → plan.md<br/>(Human review gate)"]
        TASKS["/tasks → tasks.md<br/>(Decomposed checklist)"]
        TASKSYNC["tasks.md → GitHub Issues Sync Action"]
        CONST["constitution.md<br/>(Governing principles)"]
    end

    %% LAYER 4: AGENTIC EXECUTION
    subgraph EXEC["Part V — Agentic Execution Layer"]
        WORKTREES["git worktrees<br/>Parallel, isolated workspaces"]
        PLANMODE["Plan Mode<br/>Create plan.md + wait for approval"]
        AGENTMODE["Agent Mode<br/>Implement code/tests/docs"]
        PRFLOW["Pull Request<br/>Template, Plan-SHA, review gates"]
        AGENTS["Agent Types<br/>DeveloperAgent<br/>RefactorAgent<br/>EvaluatorAgent<br/>SecurityAgent<br/>ArchitectAgent<br/>DocAgent"]
    end

    %% LAYER 5: CI/CD + EVAL
    subgraph BMAD["Part VI — CI/CD as BMAD Loop"]
        BUILD["Build<br/>Compile, test, containerize"]
        MEASURE["Measure<br/>Coverage, RAG eval, contract tests, SAST"]
        ANALYZE["Analyze<br/>AI summarizes JSON → PR comment"]
        DECIDE["Decide<br/>Close Issue + create tech-debt Issues"]
    end

    %% LAYER 6: KNOWLEDGE
    subgraph KNOW["Part VII — Knowledge Architecture"]
        DOCS["Docs-in-Repo<br/>/docs, not Wiki"]
        ADRA["Architecture Decision Records"]
        DOCAGENT["DocAgent updates docs on PR"]
    end

    TEAMS --> PROJECTS
    PROJECTS --> SPECIFY
    SPECIFY --> PLANMD
    PLANMD --> TASKS
    TASKS --> TASKSYNC
    TASKSYNC --> DISPATCH
    DISPATCH --> PLANMODE
    PLANMODE --> AGENTMODE
    AGENTMODE --> PRFLOW
    PRFLOW --> BUILD
    BUILD --> MEASURE
    MEASURE --> ANALYZE
    ANALYZE --> DECIDE
    DECIDE --> PROJECTS
    PRFLOW --> DOCAGENT
    DOCAGENT --> DOCS
```

---

# 🔷 **2. Specification-to-Execution Flow (Spec Kit Pipeline)**

This diagram visualizes the core idea of _Spec → Plan → Tasks → Implement_.

```mermaid
sequenceDiagram
    participant Human as Human Architect/PM
    participant SpecKit as Spec Kit Pipeline
    participant Agent as DeveloperAgent
    participant GitHub as GitHub Repo

    Human->>SpecKit: /specify<br/>“What + Why”
    SpecKit->>GitHub: Generate spec.md

    Human->>Agent: Trigger /plan
    Agent->>GitHub: plan.md (await review)

    Human->>GitHub: Approve plan.md

    Agent->>GitHub: tasks.md (decomposed checklist)
    Agent->>GitHub: Create worktree & begin implementation

    Agent->>GitHub: Open PR<br/>(Plan-SHA, linked tasks)
    GitHub->>Human: Request review
```

---

# 🔶 **3. Agentic Execution Lifecycle (Plan Mode → Agent Mode → PR)**

This shows how an agent executes work safely and audibly within GitHub.

```mermaid
flowchart LR
    CREATE["Issue Created<br/>(YAML Form)"]
    DISPATCH["AI Dispatcher Assigns Agent"]
    WORKTREE["Create Worktree<br/>(feature/123-xyz)"]
    PLANMODE["Plan Mode<br/>Commit PLAN.md"]
    HUMANREVIEW["Human Review<br/>(Required based on Risk/Ambiguity)"]
    AGENTMODE["Agent Mode<br/>Implement Code/Tests/Docs"]
    PR["Open Pull Request<br/>Includes Plan-SHA + template"]
    REVIEW["Human Review + QA Gates"]

    CREATE --> DISPATCH --> WORKTREE --> PLANMODE --> HUMANREVIEW --> AGENTMODE --> PR --> REVIEW
```

---

# 🔷 **4. BMAD CI/CD Loop (Build–Measure–Analyze–Decide)**

This expresses the intelligence layer of your pipeline.

```mermaid
flowchart TB
    PR["Pull Request Opened"]

    subgraph BUILD["BUILD"]
        B1["Compile"]
        B2["Unit Tests"]
        B3["Container Build"]
    end

    subgraph MEASURE["MEASURE\nEvaluatorAgents"]
        COV["Code Coverage\ncoverage.json"]
        RAG["RAG Evaluation\nrag-eval.json"]
        CT["Contract Tests\nOpenAPI / Dredd"]
        SEC["SAST Security Scan"]
    end

    subgraph ANALYZE["ANALYZE"]
        ANALYZEBOT["AI interprets JSON → produces summary\ncoverage -5%, rag fluency 0.3"]
    end

    subgraph DECIDE["DECIDE"]
        CLOSE["Close originating Issue"]
        TECHDEBT["Create tech-debt Issue automatically"]
    end

    PR --> BUILD
    BUILD --> MEASURE
    MEASURE --> ANALYZE
    ANALYZE --> DECIDE
```

---

# 🔶 **5. (Bonus) Knowledge Architecture (Docs, ADRs, DocAgent)**

```mermaid
flowchart LR
    CODE["Code Change"]
    PR["Pull Request"]
    DOCAGENT["DocAgent Triggered via Action"]
    DOCUPDATE["Update /docs and ADRs"]
    REVIEW["Human Review"]
    MERGE["Merged PR"]

    CODE --> PR --> DOCAGENT
    DOCAGENT --> DOCUPDATE --> REVIEW --> MERGE
```

---

# 🔥 **You Now Have:**

- A **top-level system diagram**
    
- A **spec pipeline diagram**
    
- An **agent execution lifecycle diagram**
    
- A **BMAD loop diagram**
    
- A **docs + ADRs knowledge diagram**
    
