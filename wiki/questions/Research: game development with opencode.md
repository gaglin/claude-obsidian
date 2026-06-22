---
type: synthesis
title: "Research: game development with opencode"
created: 2026-06-22
updated: 2026-06-22
tags:
  - research
  - game-development
  - opencode
status: developing
rounds: 2
sources_found: 5
related:
  - "[[OpenCode Game Studios]]"
  - "[[AI Game Dev Pipeline]]"
  - "[[OpenCode]]"
  - "[[opencode-game-studios-source]]"
  - "[[opencode-game-studios-striderZA-source]]"
  - "[[game-creator-source]]"
  - "[[opencode-official-docs-source]]"
  - "[[local-ai-game-build-source]]"
sources:
  - "[[opencode-game-studios-source]]"
  - "[[opencode-game-studios-striderZA-source]]"
  - "[[game-creator-source]]"
  - "[[opencode-official-docs-source]]"
  - "[[local-ai-game-build-source]]"
---

# Research: game development with opencode

## Overview

OpenCode has spawned a vibrant game development ecosystem centered on its agent architecture. The dominant pattern is the "game studio in a config" approach — defining specialized subagents (directors, programmers, artists, QA) as markdown files and invoking them via @-mentions. Multiple community projects now provide turnkey studio configurations, one-shot game pipelines, and engine-specific tooling — all running on OpenCode's free Big Pickle model.

## Key Findings

- OpenCode Game Studios provides 54 specialized agents with 37 workflow skills — the most comprehensive game dev config pack. Apply as: `cp -r .opencode/* ~/.config/opencode/` (Source: [[opencode-game-studios-source]])
- game-creator builds complete 2D (Phaser 3) and 3D (Three.js) browser games from a single description in ~10 minutes, with QA gates after every step (Source: [[game-creator-source]])
- Real-world case: a complete Snake game was built with zero manual code using OpenCode + local LLM (Qwen 3.5) on consumer hardware (Source: [[local-ai-game-build-source]])
- OpenCode's Plan Mode is the recommended architecture guardrail — design first, build second (Source: [[local-ai-game-build-source]], [[opencode-official-docs-source]])
- Multiple community forks of the OCGS framework exist, most notably striderZA's modular version with a working Pong demo game (Source: [[opencode-game-studios-striderZA-source]])
- Dedicated engine specialists exist for Godot 4, Unity 6, Unreal Engine 5, and GameMaker within OCGS (Source: [[opencode-game-studios-source]])

## Key Entities

- [[OpenCode]]: Open source AI coding agent by Anomaly; 160K+ GitHub stars, 7.5M monthly devs; free Big Pickle model

## Key Concepts

- [[OpenCode Game Studios]]: Studio hierarchy pattern — 54 agents organized in 3 tiers (directors, leads, specialists)
- [[AI Game Dev Pipeline]]: Structured approach with phases: idea → architecture → scaffold → implement → QA → deploy → monetize

## Contradictions

- No significant contradictions found across sources. All sources agree that (a) OpenCode's agent architecture is well-suited for structured game development, and (b) the free Big Pickle model makes it accessible. The main divergence is approach: OCGS provides a broad studio config while game-creator focuses on rapid browser-game generation.

## Open Questions

- How does Big Pickle's game-relevant coding performance compare to paid models (Claude, GPT) for complex game logic?
- Is there production-quality evidence of a full commercial-quality game built with OCGS (not just Pong demos)?
- What is the optimal agent count per game project? 54 agents may be overkill for small projects.
- How does the OpenCode Game Studios approach compare against dedicated game AI tools like Danya or Helm in practice?

## Sources

- [[opencode-game-studios-source]]: TraftG, 2026-03-26, GitHub. High confidence.
- [[opencode-game-studios-striderZA-source]]: striderZA, 2026-04-29, GitHub. High confidence.
- [[game-creator-source]]: PlayableIntelligence, 2026-01-28, GitHub. High confidence.
- [[opencode-official-docs-source]]: OpenCode/Anomaly, 2026, documentation. High confidence.
- [[local-ai-game-build-source]]: Technical Deck, 2026-04-09, article. High confidence.
