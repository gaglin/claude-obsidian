---
type: source
title: "Development Workflow Pattern"
created: 2026-07-16
source_type: note
related:
  - "[[Multi-Model Development Workflow]]"
  - "[[Session Handoff Protocol]]"
  - "[[Graphify]]"
  - "[[Opus 4.8]]"
  - "[[systematic-debugging]]"
  - "[[brainstorming]]"
  - "[[writing-plans]]"
status: developing
tags:
  - workflow
  - multi-model
  - development-process
---

# Development Workflow Pattern

**Source**: User's development workflow note (Chinese)
**Date**: 2026-07-16

## Core Workflow

1. **Architecture understanding**: Use Graphify to map entire app architecture, function relationships, and tool invocations
2. **Bug fixing**: Open Opus 4.8, use obra/superpowers `/systematic-debugging` to find root cause
3. **New features**: Use `/brainstorming` first, then `/writing-plans` for implementation plan
4. **Complex work**: Run `adversarial-verify` to validate plans for difficult bugs or complex features
5. **Implementation**: Use cheaper models (not Opus) for actual coding
6. **Session end**: Write `HANDOFF.md` + `MEMORY.md` recording failed approaches, decisions, known limitations
7. **Session start**: Force-read handoff files to restore context

## Key Insight

This workflow dramatically reduces the risk of "fix A, break B" problems by:
- Separating planning from execution
- Using the right model for each task
- Persisting context across sessions
- Validating plans before implementation

## Related Pages

- [[Multi-Model Development Workflow]] — the full pattern with model assignment rationale
- [[Session Handoff Protocol]] — how HANDOFF.md + MEMORY.md prevent context loss
- [[Graphify]] — architecture visualization tool
