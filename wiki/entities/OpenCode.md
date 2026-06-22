---
type: entity
title: "OpenCode"
created: 2026-06-22
updated: 2026-06-22
tags:
  - entity
  - tool
  - ai-coding-agent
  - opencode
status: developing
related:
  - "[[OpenCode Game Studios]]"
  - "[[AI Game Dev Pipeline]]"
  - "[[opencode-game-studios-source]]"
  - "[[opencode-official-docs-source]]"
  - "[[local-ai-game-build-source]]"
---

# OpenCode

An open source AI coding agent for terminal, desktop, and IDE environments. Built by Anomaly. Over 160,000 GitHub stars, 900+ contributors, 7.5M monthly developers.

## Key Features

- **Multi-model**: Supports 75+ LLM providers; free Big Pickle model included
- **Multi-session**: Run multiple agents in parallel on the same project
- **Agent system**: Primary agents (Tab-switchable) and subagents (@-mentionable)
- **Permissions**: Per-tool allow/ask/deny per agent
- **Skills**: Reusable workflow packages (slash commands)
- **Desktop app**: Beta available on macOS, Windows, Linux

## Relevance to Game Development

OpenCode's agent architecture is uniquely suited for game development because:

1. Subagent system enables role-based delegation (director, programmer, artist, QA)
2. Plan mode enforces architecture-first design before coding
3. Free Big Pickel model eliminates API cost concerns
4. Multi-session support handles long-running game projects
5. Permission system prevents autonomous agent sprawl

## Community Game Dev Ecosystem

Multiple community projects build on OpenCode for game development:

- OpenCode Game Studios (54 agents, 37 skills)
- game-creator (Phaser/Three.js one-shot pipeline)
- Various GodotMaker and Unity MCP integrations

## Resources

- Website: https://opencode.ai
- Docs: https://opencode.ai/docs
- GitHub: https://github.com/anomalyco/opencode
- Zen models: https://opencode.ai/zen
