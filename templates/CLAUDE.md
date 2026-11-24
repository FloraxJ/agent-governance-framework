# AI Assistant Project Guidelines (Claude Code / Antigravity / Cursor)

This project follows the **Agent Governance Framework**. Follow these core invariants without exception:

## 1. Consent & Behavior Invariants
- Provide architectural options in plain text BEFORE writing code.
- User complaints, cost questions, review comments, or plan bullets DO NOT constitute consent to write code.
- Write code ONLY after explicit user confirmation ("yes", "go ahead", specific option chosen).
- Game feel, physics, network protocols, and timings must NEVER be altered without explicit consent (diagnostic logging is allowed).
- No speculative fixes: reproduce with raw diagnostic numbers first, then apply fix.

## 2. Context Economy & Research
- Never read whole files unless rewriting. Limit file reads to 50–80 lines around targeted grep matches.
- Multi-file research (>2–3 files) must be delegated to an isolated subagent so that context is discarded after returning a 20–50 line summary.
- Targeted greps before any edit. Minimal line diffs. Limit tool outputs with head/tail/grep.

## 3. Code Review & Architecture
- Code must reside in its rightful domain owner. Do not couple subsystems for convenience.
- Run an independent review with an isolated subagent before claiming completion.
- Blind Review Rule: Do NOT explain "why you did it this way" to the reviewer. Provide task, rules, and diff only.
- Run automated tests ONLY after the review is clean ("no remarks").

## 4. Git & Engine Hygiene
- NEVER use `git add .`, `git add -A`, or `git commit -a`. Stage files strictly by explicit name.
- Revert editor noise and headless batch assets immediately after test runs.
- Do not create unmanaged worktrees; clean up temporary trees immediately.
