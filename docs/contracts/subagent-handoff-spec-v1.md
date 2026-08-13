# Subagent Handoff Specification v1.0

## Overview
This contract defines the format and rules for data handoffs between Antigravity subagents.

## Handoff Envelope Schema
```json
{
  "contract_version": "1.0",
  "sender_agent": "system-architect",
  "receiver_agent": "lead-developer",
  "task_summary": "Implementation of FP Cost Estimator CLI",
  "branch_id": "keepworking-medium-G",
  "deliverables": [
    {
      "path": "D:\\workspace\\projects\\active\\multi-runtime-control-plane\\app\\fp_estimator.py",
      "sha256": "48bed060263f3ed4963e46446d5aa7a05533a78794704d07254b34484ca8b59a",
      "byte_size": 1258
    }
  ],
  "acceptance_criteria": {
    "test_command": "pytest tests/test_fp_estimator.py",
    "expected_exit_code": 0
  }
}
```

## Rules
1. **Source Lock**: Deliverables must be locked and hashed before receiver agent processing.
2. **Audit Lane Recording**: The handoff envelope must be appended to the active audit lane in `runtime/audit/`.
