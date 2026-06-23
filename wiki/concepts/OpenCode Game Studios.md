---
type: concept
title: "OpenCode Game Studios"
created: 2026-06-22
updated: 2026-06-22
tags:
  - concept
  - game-development
  - opencode
  - ai-agents
status: developing
related:
  - "[[OpenCode]]"
  - "[[AI Game Dev Pipeline]]"
  - "[[opencode-game-studios-source]]"
  - "[[Research: opencode-game-studio and claude-obsidian]]"
  - "[[Agent Skills Ecosystem]]"
---

# OpenCode Game Studios

A configuration pattern that transforms OpenCode from a general-purpose AI coding agent into a structured game development studio with specialized roles, workflow skills, and quality gates.

## Architecture

Three-tier hierarchy:

- **Tier 1 — Directors**: creative-director, technical-director, producer (strategic oversight)
- **Tier 2 — Leads**: game-designer, lead-programmer, art-director, audio-director, narrative-director, qa-lead
- **Tier 3 — Specialists**: gameplay-programmer, engine-programmer, ai-programmer, level-designer, sound-designer, prototyper, and more

## Engine Support

Dedicated specialist agents for Godot 4, Unity 6, Unreal Engine 5, and GameMaker. Each engine module includes shader, scripting, and UI specialists.

## Collaboration Protocol

Every task follows: Question → Options → Decision → Draft → Approval. Agents must ask before writing, show drafts, and get explicit approval for multi-file changes.

## Ecosystem

Multiple community forks exist: TraftG (original), oshinono, striderZA (modular with demo game), Diegiwg (with model assignment strategy), Accelerator-mzq, Kazmallar.

## Relationship to claude-obsidian

Both OCGS and claude-obsidian implement the Agent Skills specification, making them interoperable. OCGS provides game development agents; claude-obsidian provides knowledge management skills. They can coexist in the same OpenCode session — OCGS agents build games while claude-obsidian vault skills document the process. Shared dependency on the Superpowers plugin further connects the ecosystems. (Source: [[Research: opencode-game-studio and claude-obsidian]])

## Key Limitation

Not compatible with Claude Code — designed specifically for OpenCode's agent architecture and free Big Pickle model.
