---
source_url: https://github.com/shanraisshan/claude-code-best-practice/blob/main/tips/claude-thariq-tips-17-mar-26.md
fetched: 2026-06-24
---

# Lessons from Building Claude Code: How We Use Skills — Thariq

A comprehensive guide on how Anthropic uses skills internally, shared by Thariq (@trq212) on March 17, 2026.

---

## Context

Skills have become one of the most used extension points in Claude Code. They're flexible, easy to make, and simple to distribute. But this flexibility also makes it hard to know what works best. Thariq shares the lessons learned from using skills extensively at Anthropic with hundreds of them in active use.

---

## What are Skills?

A common misconception is that skills are "just markdown files", but the most interesting part is that they're **folders** that can include scripts, assets, data, etc. — things the agent can discover, explore, and manipulate. Skills also have a wide variety of configuration options including registering dynamic hooks.

---

## 9 Skill Categories

After cataloging all of their skills, the team noticed they cluster into 9 recurring categories:

### 1/ Library & API Reference
Skills that explain how to correctly use a library, CLI, or SDKs. Often include a folder of reference code snippets and a list of gotchas. Examples: billing-lib, internal-platform-cli, frontend-design.

### 2/ Product Verification
Skills that describe how to test or verify code is working. Often paired with external tools like Playwright, tmux. It can be worth having an engineer spend a week making verification skills excellent. Examples: signup-flow-driver, checkout-verifier, tmux-cli-driver.

### 3/ Data Fetching & Analysis
Skills that connect to data and monitoring stacks. Include libraries to fetch data with credentials, dashboard IDs, common workflows. Examples: funnel-query, cohort-compare, grafana.

### 4/ Business Process & Team Automation
Skills that automate repetitive workflows into one command. Simple instructions, possibly with dependencies on other skills or MCPs. Saving previous results in log files helps the model stay consistent. Examples: standup-post, create-ticket, weekly-recap.

### 5/ Code Scaffolding & Templates
Skills that generate framework boilerplate for specific functions. Combine with scripts that can be composed. Useful when scaffolding has natural language requirements beyond pure code generation. Examples: new-workflow, new-migration, create-app.

### 6/ Code Quality & Review
Skills that enforce code quality and help review code. Include deterministic scripts or tools for robustness. Run automatically as hooks or inside GitHub Actions. Examples: adversarial-review, code-style, testing-practices.

### 7/ CI/CD & Deployment
Skills that fetch, push, and deploy code. May reference other skills to collect data. Examples: babysit-pr, deploy-service, cherry-pick-prod.

### 8/ Runbooks
Skills that take a symptom (Slack thread, alert, error signature), walk through multi-tool investigation, and produce a structured report. Examples: service-debugging, oncall-runner, log-correlator.

### 9/ Infrastructure Operations
Skills for routine maintenance and operational procedures, including destructive actions that benefit from guardrails. Examples: resource-orphans, dependency-management, cost-investigation.

---

## 9 Tips for Making Skills

### Tip 1: Don't State the Obvious
Focus on information that pushes Claude out of its normal way of thinking. The frontend design skill was built by iterating on improving Claude's design taste, avoiding classic patterns like the Inter font and purple gradients.

### Tip 2: Build a Gotchas Section
The highest-signal content in any skill is the Gotchas section. Build from common failure points Claude runs into when using the skill. Update over time to capture new gotchas.

### Tip 3: Use the File System & Progressive Disclosure
A skill is a folder, not just a markdown file. Use the entire file system for context engineering. Tell Claude what files are in the skill, and it will read them at appropriate times. Split detailed function signatures into `references/api.md`.

### Tip 4: Avoid Railroading Claude
Claude will generally try to stick to instructions. Give it the information it needs, but the flexibility to adapt. Instead of prescriptive step-by-step instructions, give the goal and constraints.

### Tip 5: Think through the Setup
Store setup information in a `config.json` file in the skill directory. If config is not set up, the agent can ask the user for information using structured, multiple choice questions.

### Tip 6: The Description Field Is for the Model
Claude Code scans every available skill's description at session start. The description is not a summary — it describes **when to trigger** this skill. Write it for the model.

### Tip 7: Memory & Storing Data
Store data in append-only text log files, JSON files, or SQLite. Use `${CLAUDE_PLUGIN_DATA}` as a stable folder per plugin so data persists across upgrades.

### Tip 8: Store Scripts & Generate Code
Giving Claude scripts and libraries lets it spend turns on composition rather than reconstructing boilerplate. Claude can then generate scripts on the fly to compose functionality for advanced analysis.

### Tip 9: On-Demand Hooks
Skills can include hooks activated only when the skill is called, lasting for the session duration. Examples: `/careful` blocks rm -rf, DROP TABLE, force-push; `/freeze` blocks Edit/Write outside a specific directory.

---

## Distributing Skills

Two ways: check into your repo (under `.claude/skills`) or make a plugin with a marketplace. Every checked-in skill adds a little context. As you scale, an internal marketplace lets teams decide which skills to install.

## Managing a Marketplace

No centralized team decides what goes in. Upload to a sandbox folder, point people there. When a skill gains traction, the owner PRs it into the marketplace. Curation before release prevents redundancy.

## Composing Skills

Skills can depend on each other. Reference other skills by name; the model will invoke them if installed. Dependency management is not natively built in — the model resolves the composition at runtime.

## Measuring Skills

Use a PreToolUse hook that logs skill usage. This reveals popular skills and undertriggering ones.

## Conclusion

Skills are powerful and flexible. Most started as a few lines and a single gotcha, getting better as people added to them when Claude hit new edge cases.

## Sources

- [Thariq (@trq212) on X — March 17, 2026](https://x.com/trq212/status/2033949937936085378)
- [Skilljar — Agent Skills course](https://code.claude.com/docs/en/skills)
- [Skill Creator](https://code.claude.com/docs/en/skills)
