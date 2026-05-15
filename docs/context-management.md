# Context Management

Context is limited.

Poor context management causes:

- hallucination
- stale assumptions
- contradictory decisions
- token exhaustion
- degraded reasoning
- unstable orchestration

Context must be treated as a managed resource.

---

## Context Types

Use separate categories for different memory lifetimes.

### Runtime Context

Temporary execution context.

Examples:

- current task
- active files
- recent outputs
- active blockers

Lifetime:

- current execution only

---

### Repository Memory

Persistent project memory.

Examples:

- architecture docs
- AGENTS.md
- issues
- ADRs
- operational guides

Lifetime:

- long-term

---

### Historical Context

Past reasoning and old discussions.

Useful for:

- understanding intent
- understanding tradeoffs
- recovering lost rationale

Dangerous when stale.

---

## Loading Rules

Load only context relevant to the task.

Do not:

- load the full repository history
- load all docs
- load unrelated governance files
- load stale issues without verification

Use `docs/document-routing.md`.

---

## Context Priority

Priority order:

1. current code
2. current task scope
3. task-specific docs
4. active issues
5. historical discussions
6. old chat history

Higher priority context overrides lower priority context.

---

## Context Compression

Large context should be compressed into:

- decisions
- constraints
- risks
- ownership
- unresolved blockers

Avoid replaying entire discussions.

Prefer:

- summaries
- structured decisions
- issue references
- explicit conclusions

---

## Stale Context

Old context may be invalid.

Treat context as stale when:

- code changed significantly
- architecture changed
- dependencies changed
- tests changed
- old issues were closed long ago

Verify stale context before acting on it.

---

## Context Pollution

Context pollution happens when unrelated information influences decisions.

Examples:

- old design assumptions
- outdated architecture notes
- abandoned plans
- unrelated tasks
- excessive governance text

Reduce pollution by:

- scoped reading
- targeted retrieval
- short summaries
- issue references
- explicit task boundaries

---

## Long-Term Memory Rules

Persistent memory should contain:

- architecture decisions
- operational procedures
- important failures
- migration history
- stable workflows
- recurring constraints

Persistent memory should not contain:

- temporary debugging noise
- repeated chat summaries
- speculative ideas without ownership
- abandoned drafts without status

---

## Retrieval Rules

Before loading context, ask:

- Is this directly relevant?
- Is this current?
- Is this authoritative?
- Is this worth the context cost?

More context is not automatically better.

---

## Anti-Patterns

Avoid:

- loading everything by default
- treating all context equally
- relying on old chat logs as truth
- preserving every discussion forever
- expanding context to avoid making decisions
- turning the repository into a memory dump

Focused context improves reasoning quality.
