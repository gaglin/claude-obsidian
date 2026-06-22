---
type: synthesis
title: "Research: ChatGPT as planner, OpenCode as executor for game development"
created: 2026-06-22
updated: 2026-06-22
tags:
  - research
  - game-development
  - opencode
  - chatgpt
  - workflow
status: developing
rounds: 2
sources_found: 7
related:
  - "[[Planner-Executor Workflow Pattern]]"
  - "[[OpenCode Game Studios]]"
  - "[[AI Game Dev Pipeline]]"
  - "[[OpenCode Plan Manager]]"
  - "[[OpenCode]]"
  - "[[planning-execution-separation-source]]"
  - "[[dual-llm-game-build-source]]"
  - "[[opencode-game-studios-source]]"
  - "[[opencode-game-studios-striderZA-source]]"
  - "[[local-ai-game-build-source]]"
sources:
  - "[[planning-execution-separation-source]]"
  - "[[dual-llm-game-build-source]]"
  - "[[opencode-game-studios-source]]"
  - "[[opencode-game-studios-striderZA-source]]"
  - "[[local-ai-game-build-source]]"
  - "[[opencode-official-docs-source]]"
---

# Research: ChatGPT as planner, OpenCode as executor for game development

## Overview

There is a well-established and rapidly maturing pattern of using ChatGPT (or other reasoning models) as a planning/design layer and OpenCode (with its Plan/Build dual-agent architecture) as the execution layer for game development. The pattern is supported by multiple independent implementations — from OCGS's tiered model assignment to explicit Planner->Builder tools like OpenCode Plan Manager and betterspec. The core insight: routing planning tokens to expensive reasoners and execution tokens to cheap/fast models reduces cost by ~5x while improving code quality through architectural pre-commitment and independent review.

## Key Findings

- **ChatGPT-as-planner is an established pattern**: Multiple independent sources document using ChatGPT (or GPT-5.5, Opus, Kimi K2.6) for game design documents, PRDs, architecture decisions, and implementation plans before any code is written (Source: [[planning-execution-separation-source]], [[dual-llm-game-build-source]])
- **OpenCode's Plan/Build architecture is the natural execution counterpart**: OpenCode ships with built-in Plan (read-only analysis) and Build (execution) agents, providing the infrastructure for the planner-executor split (Source: [[opencode-official-docs-source]], [[local-ai-game-build-source]])
- **OpenCode Game Studios implements tiered model assignment**: Directors (creative, technical, producer) run on reasoning-heavy models; specialists and leads run on workhorse models. Per-agent model override via config or `change_model.sh` (Source: [[opencode-game-studios-source]], [[opencode-game-studios-striderZA-source]])
- **Explicit Planner-to-Builder tools exist**: OpenCode Plan Manager provides Zod-validated plan schemas, filesystem Kanban, and cross-session continuity. betterspec adds independent validators with clean context. SDLC Wizard recipes route Opus -> GPT-5.5 review -> Sonnet builder -> GPT-5.5 implementation review with >=95% confidence gates (Source: [[planning-execution-separation-source]])
- **Cost optimization is significant**: The Planner+Executor split routes expensive reasoning tokens to planning phases only. Sorceress/WizardGenie reports ~1/5 cost vs single-frontier-model. OCGS defaults to free Big Pickle with optional premium overrides (Source: [[dual-llm-game-build-source]])
- **Cross-model review catches real bugs**: In documented dual-LLM game builds, Claude caught P0/P1 bugs introduced by ChatGPT (9 in week 1). Cross-model disagreement signaled real bugs ~70% of the time (Source: [[dual-llm-game-build-source]])
- **Full workflow proven end-to-end**: Multiple real game builds exist (Snake through OpenCode+Qwen, Pong through OCGS, Godot roguelite through ChatGPT+Claude, browser games through game-creator) all following the plan-first pattern (Source: [[local-ai-game-build-source]], [[dual-llm-game-build-source]], [[opencode-game-studios-source]])

## Key Entities

- [[OpenCode]]: Open source AI coding agent; Plan/Build dual-agent architecture
- [[OpenCode Plan Manager]]: Plugin implementing Planner->Builder pattern with Zod validation and filesystem Kanban

## Key Concepts

- [[Planner-Executor Workflow Pattern]]: Separating planning/architecture from execution across different models or agents
- [[OpenCode Game Studios]]: 54-agent studio hierarchy with tiered model assignment strategy
- [[AI Game Dev Pipeline]]: Phased pipeline with plan gates, now incorporating planner-executor split

## Contradictions

- None significant. All sources agree: (a) separating planning from execution improves quality, (b) OpenCode's architecture is well-suited for this split, (c) ChatGPT excels at design/planning tasks while other models handle execution effectively. Minor divergence on optimal model pairing: some prefer Opus+Sonnet, others GPT-5.5+DeepSeek, others Kimi+Qwen — but the pattern is the same.

## Open Questions

- What is the optimal model routing matrix per game engine, genre, and task type?
- How does the planner-executor pattern scale to teams of multiple human developers using the same config?
- Can the review gate be automated end-to-end, or does human playtesting remain the binding constraint?
- Does the pattern hold for AAA-scale projects, or is it limited to indie/vertical-slice scope?
- What happens when the planner and executor models disagree persistently — who arbitrates?

## Sources

- [[planning-execution-separation-source]]: Damilare Protocol Arikeusola, 2026-06-02. High confidence.
- [[dual-llm-game-build-source]]: GamineAI Team, 2026-05-22. High confidence.
- [[opencode-game-studios-source]]: TraftG, 2026-03-26. High confidence.
- [[opencode-game-studios-striderZA-source]]: striderZA, 2026-04-29. High confidence.
- [[local-ai-game-build-source]]: Technical Deck, 2026-04-09. High confidence.
- [[opencode-official-docs-source]]: OpenCode/Anomaly, 2026. High confidence.
