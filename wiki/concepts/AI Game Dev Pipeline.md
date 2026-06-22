---
type: concept
title: "AI Game Dev Pipeline"
created: 2026-06-22
updated: 2026-06-22
tags:
  - concept
  - game-development
  - ai-agents
  - pipeline
status: developing
related:
  - "[[OpenCode Game Studios]]"
  - "[[OpenCode]]"
  - "[[game-creator-source]]"
  - "[[local-ai-game-build-source]]"
---

# AI Game Dev Pipeline

A structured approach to building games with AI coding agents, replacing ad-hoc chat sessions with phased workflows, quality gates, and role-based agent delegation.

## Pipeline Stages

1. **Idea capture** — Game Design Document generation via interactive agent session
2. **Architecture planning** — Technical Design Document with system decomposition
3. **Scaffolding** — Project structure, build configuration, entry points
4. **Implementation** — Gameplay systems, rendering, audio (agent-written)
5. **Visual QA** — Screenshot-based validation with vision-capable models
6. **Playtesting** — Automated runtime verification with headless browsers
7. **Deployment** — Web (Vite/Cloudflare), Unity build, Godot export
8. **Monetization** — Play.fun SDK, leaderboards, anti-cheat

## Key Patterns

- EventBus architecture for cross-module communication (game-creator pattern)
- GameState as single source of truth with `reset()` for clean restarts
- Constants file — zero hardcoded values in game logic
- Plan Mode before Build Mode (OpenCode workflow)
- QA gates after every code-modifying step
- **Planner-Executor split**: ChatGPT/GPT-5.5/Opus for design docs and architecture; OpenCode Build agent/Sonnet for implementation; separate reviewer model with fresh context
- **Multi-model assignment**: directors on heavy reasoning models, specialists on workhorse models, per-agent model override
- **Confidence gates**: measurable quality thresholds (>=95%) before build and before merge
- **Filesystem persistence**: plans as plain files survive session boundaries

## Tool Ecosystem

| Tool | Engine | Agent Platform | Approach |
|------|--------|----------------|----------|
| OCGS | Any | OpenCode | Studio hierarchy (54 agents) |
| game-creator | Phaser/Three.js | 40+ agents | One-shot pipeline (~10 min) |
| GodotMaker | Godot 4 | Claude Code, Codex | GDD-driven iteration |
| Helm | Unity 6 | Claude Code | 5 agents, 6-stage pipeline |
| Danya | Any | Terminal-native | Gate chain quality control |
| gamekit | Unity | Claude Code | MCP-based Unity integration |
