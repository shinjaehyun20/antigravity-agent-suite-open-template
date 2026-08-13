# Architecture Overview — Antigravity Master Agent Suite

## High-Level Architecture
The Antigravity Agent Suite organizes 28 specialized subagents into functional clusters. Each cluster handles a distinct domain of software engineering, design, cost estimation, or operations.

```mermaid
flowchart TB
    subgraph Control ["Orchestration & Control"]
        WO[workflow-orchestrator]
        TWO[team-work-orchestrator]
        TWV[team-work-verifier]
    end

    subgraph Architecture ["Architecture & Database"]
        SA[system-architect]
        LD[lead-developer]
        AQV[audit-qa-verifier]
        DBA[database-graph-architect]
    end

    subgraph Cost ["Requirements & Costing"]
        SRS[requirements-spec-analyst]
        FPE[function-point-estimator]
    end

    subgraph Design ["Design & Publishing"]
        Figma[figma-app-uiux-designer]
        WebPub[web-publishing-specialist]
        DSF[design-system-formatter]
        ArtDir[creative-visual-art-director]
    end

    subgraph Media ["3D, Video & Games"]
        VMS[video-media-synthesis-specialist]
        G3D[game-3d-unreal-blender-engine-developer]
    end

    Control --> Architecture
    Control --> Cost
    Control --> Design
    Control --> Media
```

## Key Principles
1. **Decoupled Autonomy**: Each subagent runs in its own context window with specialized tools and non-negotiable system prompts.
2. **Deterministic Lifecycle**: Every task follows `goal → worktree → evidence → acceptance gate`.
3. **Auditability**: Execution traces and receipts are saved to `runtime/audit/YYYY-MM-DD/`.
