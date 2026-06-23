---
type: meta
title: "Wiki Index"
updated: 2026-04-07
tags:
  - meta
  - index
status: evergreen
related:
  - "[[overview]]"
  - "[[log]]"
  - "[[hot]]"
  - "[[dashboard]]"
  - "[[Wiki Map]]"
  - "[[concepts/_index]]"
  - "[[entities/_index]]"
  - "[[sources/_index]]"
  - "[[LLM Wiki Pattern]]"
  - "[[Hot Cache]]"
  - "[[Compounding Knowledge]]"
  - "[[Andrej Karpathy]]"
---

# Wiki Index

Last updated: 2026-06-22 | Total pages: 47 | Sources ingested: 9

Navigation: [[overview]] | [[log]] | [[hot]] | [[dashboard]] | [[Wiki Map]] | [[getting-started]]

---

## Concepts

- [[LLM Wiki Pattern]] — the pattern for building persistent, compounding knowledge bases using LLMs (status: mature)
- [[Hot Cache]] — ~500-word session context file, updated after every ingest and session (status: mature)
- [[Compounding Knowledge]] — why wiki knowledge grows more valuable over time, unlike RAG (status: mature)
- [[cherry-picks]] — prioritized feature backlog from ecosystem research; 13 features to add to claude-obsidian (status: current)
- [[SVG Diagram Style Guide]] — canonical visual style for all diagrams: Space Grotesk, #0A0A0A dark theme, #E07850 accent, full design tokens (status: evergreen)
- [[Pro Hub Challenge]] — community challenge pattern for building claude-seo/claude-blog extensions; first challenge produced 6 submissions, 5 integrated in v1.9.0 (status: evergreen)
- [[Semantic Topic Clustering]] — SERP-based keyword grouping replacing paid tools; hub-spoke architecture with interactive visualization (status: evergreen)
- [[Search Experience Optimization]] — "read SERPs backwards" methodology for page-type mismatch detection and persona scoring (status: evergreen)
- [[SEO Drift Monitoring]] — "git for SEO" baseline/diff/track with 17 comparison rules and SQLite persistence (status: evergreen)
- [[DragonScale Memory]] — memory-layer spec inspired by the Heighway dragon curve; fold operator, deterministic page addresses, semantic tiling, boundary-first autoresearch (status: shipped v0.4, all four mechanisms opt-in)
- [[Persistent Wiki Artifact]]: durable Markdown page as the LLM's memory object, distinct from ephemeral chat turns (status: developing)
- [[Source-First Synthesis]]: provenance discipline; raw sources stay immutable while the wiki layer is synthesized and cited (status: developing)
- [[Query-Time Retrieval]]: wiki query path synthesizes with citations; complementary to Obsidian's in-vault search (status: developing)
- [[OpenCode Game Studios]] — studio-in-a-config pattern: 54 specialized agents, 37 workflow skills, 100% free on Big Pickle (status: developing)
- [[AI Game Dev Pipeline]] — structured approach to building games with AI coding agents: phases, quality gates, role-based delegation (status: developing)
- [[Planner-Executor Workflow Pattern]] — multi-model pattern: ChatGPT/Opus plans, OpenCode/Sonnet executes, independent reviewer gates (status: developing)
- [[Agent Skills Ecosystem]] — cross-platform Agent Skills standard that makes OCGS and claude-obsidian interoperable; shared spec from kepano/obsidian-skills (36K+ stars) (status: developing)
---

## Entities

- [[Andrej Karpathy]] — AI researcher, creator of the LLM Wiki pattern, former Tesla AI director (status: developing)
- [[Ar9av-obsidian-wiki]] — multi-agent compatible LLM Wiki plugin; delta tracking manifest (status: current)
- [[Nexus-claudesidian-mcp]] — native Obsidian plugin + MCP bridge; workspace memory, task management (status: current)
- [[ballred-obsidian-claude-pkm]] — goal cascade PKM; auto-commit hooks, /adopt command (status: current)
- [[rvk7895-llm-knowledge-bases]] — 3-depth query system, Marp slides, parallel deep research (status: current)
- [[kepano-obsidian-skills]] — official skills from Obsidian creator; defuddle, obsidian-bases (status: current)
- [[Claudian-YishenTu]] — native Obsidian plugin embedding Claude Code; plan mode, @mention (status: current)
- [[Claude SEO]] — Tier 4 Claude Code skill for SEO analysis; 23 skills, 17 agents, 30 scripts at v1.9.0 (status: evergreen)
- [[OpenCode]] — open source AI coding agent; 160K+ GitHub stars, 7.5M monthly devs; agent-based architecture suited for game dev (status: developing)
- [[OpenCode Plan Manager]] — OpenCode plugin implementing Planner->Builder pattern with Zod-validated schemas and filesystem Kanban (status: developing)

---

## Sources

- [[claude-obsidian-ecosystem-research]] — 2026-04-08 | web research across 16+ repos | 8 wiki pages created
- [[opencode-game-studios-source]] — 2026-03-26 | OpenCode Game Studios config pack by TraftG
- [[opencode-game-studios-striderZA-source]] — 2026-04-29 | Modular OCGS fork with Pong demo
- [[game-creator-source]] — 2026-01-28 | Automated browser game pipeline by PlayableIntelligence
- [[opencode-official-docs-source]] — 2026 | OpenCode agents documentation
- [[local-ai-game-build-source]] — 2026-04-09 | Building games with OpenCode + local LLMs
- [[planning-execution-separation-source]] — 2026-06-02 | ChatGPT planning + OpenCode execution workflow
- [[dual-llm-game-build-source]] — 2026-05-22 | ChatGPT draft + Claude review dual-LLM game build
- [[Research: opencode-game-studio and claude-obsidian]] — 2026-06-23 | synthesis: intersectional research

---

## Questions

- [[How does the LLM Wiki pattern work]] — how the pattern works and why it outperforms RAG at human scale (status: developing)
- [[Research: game development with opencode]] — synthesis: game dev ecosystem built on OpenCode's agent architecture (status: developing)
- [[Research: ChatGPT as planner OpenCode as executor]] — synthesis: ChatGPT-as-planner + OpenCode-as-executor workflow pattern for game studios (status: developing)
- [[Research: opencode-game-studio and claude-obsidian]] — synthesis: how OCGS and claude-obsidian relate architecturally; shared platform, no direct integration, complementary workflows (status: developing)

---

## Comparisons

- [[Wiki vs RAG]] — when to use a wiki knowledge base versus RAG; verdict: wiki wins at <1000 pages
- [[claude-obsidian-ecosystem]] — feature matrix of 16+ Claude+Obsidian projects; where claude-obsidian wins and gaps

---

## Decisions

- [[2026-04-14-community-cta-rollout]] - Skool community CTA footer added to 6 skill repos with per-tool frequency rules (status: active)
- [[2026-04-15-slides-and-release-session]] - Claude SEO v1.9.0 slides (15-slide HTML deck) + GitHub release v1.9.0 with PDF asset (status: complete)
- [[2026-04-15-release-report-session]] - Claude SEO v1.9.0 Release Report PDF: dark theme, 13 pages, WeasyPrint layout fixes, Challenge v2 added (status: complete)
- [[2026-04-14-claude-seo-v190-session]] - Claude SEO v1.9.0 Pro Hub Challenge integration: 5 submissions, 4 new skills, 4 review rounds, cybersecurity audit (status: complete)

---

## Domains

<!-- Add domain entries here after scaffold -->
