---
type: concept
title: "Session Handoff Protocol"
created: 2026-07-16
related:
  - "[[Multi-Model Development Workflow]]"
  - "[[Development Workflow Pattern]]"
status: developing
tags:
  - workflow
  - session-persistence
  - memory
  - handoff
---

# Session Handoff Protocol

Two files that preserve context across AI coding sessions, preventing knowledge loss and repeated mistakes.

## HANDOFF.md

Records what happened in the session:

```markdown
## Session: [date]
### Completed
- [what was done]

### Failed Approaches
- [what was tried and didn't work]

### Decisions Made
- [key decisions and rationale]

### Known Limitations
- [current constraints]

### Next Steps
- [what to do next session]
```

## MEMORY.md

Persists long-term knowledge:

```markdown
## Project Memory
### Architecture Notes
- [structural understanding]

### Gotchas
- [things that will bite you]

### Conventions
- [established patterns]

### Unresolved Questions
- [open questions]
```

## Usage Protocol

1. **Session end**: Write both files with honest assessment
2. **Session start**: Force-read both files before any work
3. **During session**: Update files as new decisions are made

## Why It Works

- Prevents "fix A, break B" by knowing what was tried
- Preserves architectural understanding across sessions
- Documents failed approaches to avoid repeating them
- Creates institutional memory that survives model context limits

## Related

- [[Multi-Model Development Workflow]] — the workflow that uses this protocol
- [[Development Workflow Pattern]] — the user's specific implementation
