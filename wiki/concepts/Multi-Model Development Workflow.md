---
type: concept
title: "Multi-Model Development Workflow"
created: 2026-07-16
related:
  - "[[Development Workflow Pattern]]"
  - "[[Opus 4.8]]"
  - "[[systematic-debugging]]"
  - "[[brainstorming]]"
  - "[[writing-plans]]"
  - "[[Session Handoff Protocol]]"
status: developing
tags:
  - workflow
  - multi-model
  - cost-optimization
  - planning-execution-separation
---

# Multi-Model Development Workflow

A structured approach to software development that assigns different AI models to tasks based on their strengths, reducing "fix A, break B" risk.

## Pattern

```
Planning Phase (expensive models):
  Opus 4.8 + systematic-debugging → root cause
  Opus 4.8 + brainstorming → feature design
  Opus 4.8 + writing-plans → implementation plan
  adversarial-verify → plan validation

Execution Phase (cheaper models):
  Sonnet / DeepSeek / GPT-5.4 → implementation
  Handoff files → session persistence
```

## Why It Works

1. **Planning requires reasoning depth** — Opus 4.8 excels at complex analysis
2. **Execution is repetitive** — cheaper models handle implementation well
3. **Verification catches drift** — adversarial review before coding prevents wasted effort
4. **Handoff prevents context loss** — MEMORY.md + HANDOFF.md preserve decisions across sessions

## Model Assignment

| Task | Model | Why |
|------|-------|-----|
| Bug diagnosis | Opus 4.8 | Deep reasoning for root cause |
| Feature brainstorming | Opus 4.8 | Creative exploration |
| Plan writing | Opus 4.8 | Structured output |
| Plan verification | Opus 4.8 | Adversarial thinking |
| Implementation | Sonnet/GPT-5.4 | Cost-efficient, fast |

## Anti-Patterns

- Using Opus for all tasks (wasteful)
- Skipping planning to jump into coding (risky)
- Not reading handoff files at session start (context loss)
- No verification before implementation (drift)

## Related

- [[Development Workflow Pattern]] — the user's specific workflow description
- [[Session Handoff Protocol]] — HANDOFF.md + MEMORY.md format
- [[Planner-Executor Workflow Pattern]] — related multi-model pattern from ecosystem research
