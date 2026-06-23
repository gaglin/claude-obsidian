---
type: synthesis
title: "Research: opencode-game-studio and claude-obsidian"
created: 2026-06-23
updated: 2026-06-23
tags:
  - research
  - opencode
  - game-development
  - claude-obsidian
  - agent-architecture
status: developing
rounds: 2
sources_found: 3
related:
  - "[[OpenCode Game Studios]]"
  - "[[OpenCode]]"
  - "[[Agent Skills Ecosystem]]"
  - "[[claude-obsidian-ecosystem]]"
  - "[[OpenCode Plan Manager]]"
  - "[[Research: game development with opencode]]"
  - "[[Research: ChatGPT as planner OpenCode as executor]]"
sources:
  - "[[opencode-game-studios-source]]"
  - "[[opencode-game-studios-striderZA-source]]"
  - "[[claude-obsidian-ecosystem-research]]"
  - "[[opencode-official-docs-source]]"
---

# Research: opencode-game-studio and claude-obsidian

## Overview

opencode-game-studio (OCGS) and claude-obsidian are independent projects with no direct integration, but they share a deep architectural kinship. Both are Agent Skills-compatible configurations that transform a general-purpose AI coding agent (OpenCode or Claude Code) into a specialized tool — one for game development, one for knowledge management. They run on the same platform (OpenCode), follow the same Agent Skills specification, and can coexist in the same user's environment with complementary workflows.

## Key Findings

- **No direct integration exists**: Neither project references the other in its README, docs, or code. They were built independently by different authors (TraftG / striderZA / Diegiwg for OCGS; AgriciDaniel for claude-obsidian) (Source: [[opencode-game-studios-source]], [[claude-obsidian-ecosystem-research]])

- **Shared platform**: Both run on OpenCode. OCGS configures `.opencode/agents/` + `.opencode/skills/` for game dev roles. Claude-obsidian installs as `~/.opencode/skills/claude-obsidian/`. OpenCode auto-discovers all skills under this path (Source: [[opencode-official-docs-source]], [[opencode-game-studios-source]])

- **Same Agent Skills spec**: Both implement the Agent Skills specification from kepano/obsidian-skills (36K+ stars). This means skill files from either project are cross-compatible — an OCGS game designer agent could load claude-obsidian vault skills, and vice versa (Source: [[claude-obsidian-ecosystem-research]])

- **Superpowers as shared dependency**: striderZA/OCGS lists the Superpowers plugin as a dependency — the same plugin claude-obsidian uses for brainstorming, TDD, code review, writing plans, and parallel agent dispatch. This is the strongest existing connective tissue between the ecosystems (Source: [[opencode-game-studios-striderZA-source]])

- **Complementary workflows**: OCGS agents (directors, leads, specialists) handle game design, implementation, and QA. Claude-obsidian skills (wiki-ingest, save, wiki-query) handle documentation, knowledge persistence, and cross-session memory. A combined workflow: OCGS agents build a game while claude-obsidian documents architecture decisions, design rationale, and playtest findings to the vault (Source: [[opencode-game-studios-source]], [[claude-obsidian-ecosystem-research]])

- **Analogous architecture mapping**: OCGS organizes 54 agents into a 3-tier studio hierarchy (directors → leads → specialists). Claude-obsidian organizes 15 skills into a knowledge management pipeline (ingest → file → query → lint → fold). Both impose structure on an otherwise unstructured AI session — one for building games, one for building knowledge (Source: prior analysis)

- **Growing ecosystem around Obsidian+OpenCode**: At least 8 other projects connect OpenCode to Obsidian (OpenGem, BYOAO, dpf-obsidian-wiki, EchoesVault, honam867/obsidian-memory-layer-mcp, r007b34r/opencode-obsidian-knowledge-workflow, xeaser/opencode-obsidian-sync, alex-kart/claude-obs). Claude-obsidian is the most comprehensive (15 skills, multi-writer safe, methodology modes, hybrid retrieval) (Source: [[claude-obsidian-ecosystem-research]])

## Key Entities

- [[OpenCode]]: Open source AI coding agent; platform that runs both OCGS and claude-obsidian
- [[OpenCode Game Studios]]: 54-agent game dev studio config pack; OCGS for short
- [[kepano-obsidian-skills]]: Obsidian creator's Agent Skills repo; 36K+ stars, defines the cross-platform skill format
- [[Claudian-YishenTu]]: Native Obsidian plugin embedding Claude Code; supports OpenCode backend

## Key Concepts

- [[Agent Skills Ecosystem]]: Cross-platform standard for AI agent skill files; OCGS and claude-obsidian both implement it
- [[Planner-Executor Workflow Pattern]]: Related pattern complementing both — ChatGPT plans, OpenCode executes, vault documents

## How They Could Work Together

A user with both projects installed could operate in this workflow:

1. **Start a game project**: `@creative-director` via OCGS to scope the game idea, produce a GDD
2. **Document decisions**: `/save` via claude-obsidian to file the GDD and architecture decisions into the wiki vault
3. **Implement iteratively**: `@lead-programmer` → `@godot-specialist` for engine work via OCGS
4. **Log findings**: wiki-ingest captures playtest results, bug reports, design changes
5. **Query accumulated knowledge**: wiki-query surfaces past decisions, preventing re-derivation
6. **Fold history**: wiki-fold rolls up the game's development log into meta-pages

The vault itself becomes the game's living design document — always up to date, cross-referenced, and queryable by both the human and AI agents.

## Contradictions

- No contradictions found. OCGS and claude-obsidian target different domains (game dev vs. knowledge management) and are not in competition. The only tension is user attention: a developer choosing between OCGS agents and claude-obsidian skills for the same session needs to be intentional about which agent/skill to invoke for a given task.

## Open Questions

- Could OCGS agents be configured to call claude-obsidian's vault skills as a quality gate? E.g., `@lead-programmer` auto-calls `/save` after completing a milestone?
- Would a combined starter config (both OCGS agents + claude-obsidian skills in one `.opencode/`) cause conflicts?
- Does the OCGS "game design document" workflow naturally map to claude-obsidian's wiki structure (sources → concepts → entities)?
- Can the Superpowers plugin dispatch OCGS agents and claude-obsidian skills in the same multi-agent workflow?

## Sources

- [[opencode-game-studios-source]]: TraftG, 2026-03-26, GitHub. High confidence.
- [[opencode-game-studios-striderZA-source]]: striderZA, 2026-04-29, GitHub. High confidence.
- [[claude-obsidian-ecosystem-research]]: 2026-04-08, web research. High confidence.
- [[opencode-official-docs-source]]: OpenCode/Anomaly, 2026, documentation. High confidence.
