---
type: concept
title: "Planner-Executor Workflow Pattern"
created: 2026-06-22
updated: 2026-06-22
tags:
  - concept
  - game-development
  - ai-agents
  - workflow
  - architecture
status: developing
related:
  - "[[OpenCode Game Studios]]"
  - "[[AI Game Dev Pipeline]]"
  - "[[OpenCode Plan Manager]]"
  - "[[OpenCode]]"
  - "[[planning-execution-separation-source]]"
  - "[[dual-llm-game-build-source]]"
---

# Planner-Executor Workflow Pattern

A multi-model AI development pattern where one model (or agent) handles planning, architecture, and design while another handles implementation and execution. This separation of concerns improves code quality, reduces context drift, and optimizes cost by routing each task to the model best suited for it.

## Core Architecture

```
[Human Idea]
    |
    v
[Planner Model] -- ChatGPT, Opus, GPT-5.5, Kimi K2.6
    |  Design docs, GDD, PRD/FRD, architecture decisions
    |  Read-only analysis, no code generation
    v
[Plan Artifact] -- Design doc, spec, task breakdown, milestone plan
    |
    v
[Executor Model] -- OpenCode Build agent, Sonnet, DeepSeek, Qwen
    |  Code generation, implementation, file writes
    |  Follows plan precisely, manages task state
    v
[Reviewer Model] -- Claude, GPT-5.5, independent validator
    |  Adversarial review, edge case detection, security audit
    |  Fresh context, zero build history bias
    v
[Human Gate] -- Playtest, integration, merge decision
```

## Implementations

### OpenCode Native Plan/Build (built-in)

OpenCode ships dual-agent architecture: Plan agent (read-only analysis, identifies cross-file dependencies, presents multi-step plan) and Build agent (executes approved plans). Toggle with Tab key.

### OpenCode Game Studios Tiered Assignment

Director agents (creative-director, technical-director, producer) run on heavy reasoning models for strategic planning. Department leads and specialists run on balanced workhorse models. Per-agent model override via `opencode.json` or `change_model.sh`.

### OpenCode Plan Manager (yurihbm)

Explicit Planner-to-Builder two-agent hierarchy with Zod-validated schemas, filesystem Kanban (pending/in_progress/done folders), cross-session continuity, and selective context loading (summary/spec/plan/full views).

### betterspec Multi-Agent SDLC

Four specialized agents: Planner (Opus — transforms proposals into specs), Builder (Sonnet — implements tasks), Validator (Sonnet — independent verification with clean context), Archivist (Sonnet — archives and extracts capabilities).

### SDLC Wizard Recipe

Multi-model routing: Opus 4.8 max planner -> GPT-5.5 xhigh plan review -> Sonnet builder -> GPT-5.5 xhigh implementation review. Confidence gates at 95% before build and before merge.

## Cost Optimization

The Planner+Executor split routes expensive reasoning tokens to planning phases and cheap generation tokens to execution phases. Sorceress/WizardGenie reports ~1/5 cost of single-frontier-model sessions. OCGS defaults to free Big Pickle with premium per-agent overrides.

## Key Principles

- **Plan Mode before Build Mode** — architectural integrity established before any code is written
- **Fresh context per reviewer** — independent verification catches same-model blind spots
- **Cross-model disagreement** — when planner and executor disagree, the bug is real ~70% of the time
- **Confidence gates** — measurable quality thresholds before state transitions
- **Filesystem persistence** — plans as plain files survive session boundaries

## Open Questions

- What is the optimal model routing for a given game engine/task type?
- How does the pattern scale to teams of human + AI collaborators?
- Can the planner-executor split be automated end-to-end, or does human review remain essential?
