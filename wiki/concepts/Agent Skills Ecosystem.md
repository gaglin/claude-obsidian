---
type: concept
title: "Agent Skills Ecosystem"
created: 2026-06-23
updated: 2026-06-23
tags:
  - concept
  - agent-architecture
  - opencode
  - claude-code
  - interoperability
status: developing
related:
  - "[[OpenCode Game Studios]]"
  - "[[OpenCode]]"
  - "[[kepano-obsidian-skills]]"
  - "[[claude-obsidian-ecosystem]]"
  - "[[Research: opencode-game-studio and claude-obsidian]]"
---

# Agent Skills Ecosystem

The cross-platform standard (Agent Skills specification at agentskills.io) that allows skill files to work across multiple AI coding agents — Claude Code, OpenCode, Codex CLI, Cursor, Windsurf, Gemini CLI, and 35+ others. This is the connective tissue that makes opencode-game-studio and claude-obsidian interoperable.

## Shared Standard

Both OCGS and claude-obsidian implement the Agent Skills specification:

| Capability | OCGS | claude-obsidian |
|------------|------|-----------------|
| Skills dir | `.opencode/skills/` | `~/.opencode/skills/claude-obsidian/` |
| Agent defs | `.opencode/agents/*.md` | `agents/*.md` |
| Commands | `.opencode/commands/` | — |
| Rules | `.opencode/rules/` | — |
| Platform | OpenCode | OpenCode / Claude Code / Codex |
| Agent count | 54 (game roles) | 15 (knowledge skills) |

## Why This Matters for the Intersection

Because both projects follow the same spec:

1. **Skills are portable**: An OCGS skill (`/sprint-plan`) and a claude-obsidian skill (`/save`) can coexist in the same OpenCode session
2. **No config conflicts**: Skills and agents live in separate directories; they don't collide
3. **Single discovery path**: OpenCode auto-discovers all SKILL.md files under `~/.opencode/skills/` — both projects' skills appear in the same @-mention menu
4. **Superpowers plugin bridges them**: Listed as a dependency in both ecosystems, providing structured workflows (brainstorming, TDD, writing plans, code review, parallel agent dispatch) usable by either OCGS agents or claude-obsidian skills

## Related Standard-Setters

- [[kepano-obsidian-skills]]: The canonical reference implementation from Obsidian's creator (36K+ stars). Defines defuddle, obsidian-markdown, obsidian-bases, json-canvas, obsidian-cli
- [[claude-obsidian-ecosystem]]: Feature matrix of 16+ projects implementing variations on the LLM Wiki + Agent Skills pattern
