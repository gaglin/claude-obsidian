---
type: source
source_type: article
title: "I Built a Game with ChatGPT and Claude - What Happened in 2026 (Honest Log)"
author: GamineAI Team
url: https://gamineai.com/blog/i-built-a-game-with-chatgpt-and-claude-heres-what-happened-2026
date_published: 2026-05-22
confidence: high
key_claims:
  - ChatGPT handled drafting (design docs, GDScript v1, UI copy); Claude handled review (refactor, threat modeling)
  - Dual-LLM workflow: ChatGPT generate -> human integrate -> Claude review -> human playtest -> merge
  - Claude caught P0/P1 bugs that ChatGPT introduced (9 in week 1)
  - Acceptance tests in design prompts became playtest checklists
  - Cross-model disagreement signaled real bugs 70% of the time
  - AI compressed typing time, not decision time; calendar was ~4 weeks part-time
related:
  - "[[Planner-Executor Workflow Pattern]]"
  - "[[AI Game Dev Pipeline]]"
  - "[[OpenCode]]"
---

# Source: Building a Game with ChatGPT and Claude

A detailed 12-day build diary of a Godot 4.x roguelite vertical slice using ChatGPT as drafter and Claude as reviewer. Includes exact prompts, BUILD_RECEIPT format, and honest failure modes.

## Key Contributions

- Defines clear role boundaries: drafter (ChatGPT), reviewer (Claude), integrator (human)
- Documents concrete bug catches: export variables, signal naming, autoload ordering
- Proves dual-LLM workflow compresses typing time but not decision time
- Provides copy-paste prompt templates for feature briefs and review passes

## Confidence

**High** — published with educational video, BUILD_RECEIPT JSON, day-by-day diary, and reproducible prompts.
