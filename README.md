# Agent Governance Framework

A battle-tested set of constraints, invariants, and workflows designed to run autonomous AI coding agents safely in production codebases (Antigravity, Claude Code, Cursor, Aider).

## Overview

Most AI prompts focus on generating code quickly. In complex projects with large repositories, multi-gigabyte caches, and active human developers, unconstrained agents create severe operational risks:
- Context exhaustion and degraded reasoning;
- Unsolicited rewrites driven by misinterpreting discussion as consent;
- Polluted Git histories from staging editor metadata and cache files;
- Speculative patches applied without concrete telemetry.

This framework introduces a formal governance layer that enforces strict engineering invariants, context budgeting, and staged review pipelines.

---

## Architecture

```text
agent-governance-framework/
├── core/
│   ├── engineering-invariants.md    # Consent criteria, measurement-first rule
│   ├── context-economy.md           # Selective file reading, disposable research subagents
│   ├── code-review-cycle.md         # Staged blind reviews, separation of concerns
│   ├── auto-model-router.md         # Multi-model routing and reasoning ceilings
│   └── session-handoff.md           # Structured context transfer across sessions
├── modules/
│   ├── gamedev-heavy-engines/       # Unity/Unreal repo hygiene, worktree isolation, deterministic tests
│   └── distributed-agents/          # Runner synchronization and environment protection
└── templates/
    ├── CLAUDE.md                    # Ready-to-use template for Claude Code
    └── .cursorrules                 # Ready-to-use rules for Cursor IDE
```

---

## Core Invariants

1. **Clarify Before Code:** Explicit distinction between exploring issues and receiving consent to change code.
2. **Telemetry First:** Bug fixes in timing, networking, or physics require raw telemetry before code changes are made.
3. **Disposable Subagents:** Deep research across multiple files is offloaded to ephemeral subagents whose context is destroyed upon returning a concise summary.
4. **Blind Review Loops:** Changes undergo independent review before test execution to ensure architectural soundess before runtime verification.
5. **Strict Named Staging:** Mass staging (`git add .`) is prohibited to prevent commiting editor artifacts and binary noise.

---

## License

Open-source under Apache-2.0 or MIT.
