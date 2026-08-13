# AGENTS.md — Antigravity Agent Suite Governance & Runtime Contract

## Purpose
This repository is the canonical registry for the 28 specialized Antigravity subagents. All agent definitions conform to the cross-runtime operating contract and enforce non-negotiable execution discipline.

## Ownership & Boundaries
- **Primary Runtime Owner**: `antigravity` / `gemini`
- **Write Boundary**:
  - `subagents/`: JSON definition files (Read-Only reference / Copy-Edit staging)
  - `docs/`: Architecture specifications and handoff contracts
- **Source Immutability**: Production reference templates and canonical master spreadsheets must never be mutated directly. All mutations occur on local staging copies in `runtime/tmp/` and undergo SHA256 integrity scans before replacement.

## Handoff Protocol (`handoff_envelope`)
All inter-agent handoffs between `workflow-orchestrator`, `system-architect`, `lead-developer`, and verifiers must declare:
1. `task_summary`: High-level summary of the handoff unit
2. `branch_id`: Unique execution branch slug
3. `scope`: Array of explicit file paths or resource URIs
4. `audit_lane`: Directory path where execution logs are stored
5. `success_criteria`: Quantitative metrics (byte size, SHA256 hash, exit code 0)

## Verification Gate
- Every task completion claim must be validated by an independent verifier (`audit-qa-verifier` or `team-work-verifier`).
- Self-declared completion without empirical proof (file byte size, test exit code 0) is strictly invalid.
