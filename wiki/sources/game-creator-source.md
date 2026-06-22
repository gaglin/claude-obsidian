---
type: source
source_type: github
title: "game-creator"
author: PlayableIntelligence
url: https://github.com/PlayableIntelligence/game-creator
date_published: 2026-01-28
confidence: high
key_claims:
  - Converts game descriptions to playable browser games in ~10 minutes
  - 2D (Phaser 3) and 3D (Three.js) engine support
  - QA subagent runs after every code step
  - Built-in deployment and monetization pipeline
  - Works with 40+ AI coding agents
related:
  - "[[AI Game Dev Pipeline]]"
---

# Source: game-creator

An opinionated Agent Skills plugin that builds complete 2D and 3D browser games from a single description. Orchestrates code writing, pixel art generation, audio, deployment, and monetization.

## Key Contributions

- `/viral-game` one-shot pipeline: scaffold → pixel art → design → audio → deploy → monetize
- EventBus/GameState/Constants architecture pattern
- QA gates after every step: build, runtime, gameplay, architecture, visual
- 8 example games (Flappy Bird, Barn Defense, Vampire Survivors, flight simulator, etc.)
- Playwright-based QA with auto-fix (up to 3 retries per step)
- Play.fun monetization integration

## Confidence

**High** — 196 GitHub stars, 8 working example games, active development with 189 commits.
