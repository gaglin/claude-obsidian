---
type: source
source_type: github
title: "OpenCode Game Studios"
author: TraftG
url: https://github.com/TraftG/opencode-game-studio
date_published: 2026-03-26
confidence: high
key_claims:
  - 54 specialized AI agents organized in studio hierarchy
  - 37 slash-command workflow skills
  - 100% free on OpenCode's Big Pickle model
  - Collaboration protocol: Question → Options → Decision → Draft → Approval
  - Engine specialists for Godot, Unity, Unreal, GameMaker
related:
  - "[[OpenCode Game Studios]]"
  - "[[OpenCode]]"
---

# Source: OpenCode Game Studios

A drop-in OpenCode configuration that provides 54 specialized agents organized in a 3-tier studio hierarchy: Directors (strategic), Department Leads, and Specialists. Includes 37 workflow skills for common game development tasks.

## Key Contributions

- Turnkey solution: `cp -r .opencode/* ~/.config/opencode/` then run `opencode`
- Collaboration protocol prevents autonomous agent sprawl
- Engine-specific specialists for Godot, Unity, Unreal, GameMaker
- All agents default to `opencode/big-pickle` (free, no API costs)
- MIT licensed

## Confidence

**High** — multiple community forks exist (oshinono, Diegiwg, striderZA), DEV.to article with engagement, demo game (OCGS-Pong) proves the workflow.
