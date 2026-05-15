# GitHub Issue Protocol

GitHub Issues are persistent project memory.

Runtime context is temporary.

Important coordination and decisions must survive beyond a single session.

---

# Purpose

Use GitHub Issues to:

- track progress
- track blockers
- track risks
- preserve architecture reasoning
- preserve review findings
- coordinate agents
- preserve operational history

The repository should remain understandable without chat history.

---

# What Should Be Recorded

Record when useful:

- plans
- implementation phases
- unresolved questions
- architectural tradeoffs
- major bugs
- regressions
- rollback events
- validation failures
- review findings
- production incidents

Avoid recording meaningless noise.

---

# Agent Coordination

Multi-agent coordination should not rely only on transient memory.

Important coordination artifacts should be persisted:

- ownership
- task boundaries
- blocked dependencies
- review requests
- validation results
- unresolved risks

This reduces:

- duplicated work
- conflicting assumptions
- hidden failures
- context loss

---

# Issue Quality

Good issues are:

- specific
- actionable
- reproducible
- scoped
- evidence-based

Good issues include:

- expected behavior
- current behavior
- reproduction steps
- affected files
- logs if useful
- risks
- related PRs or commits

---

# Architectural Decisions

Architecture decisions should be traceable.

Record:

- why the decision exists
- alternatives considered
- tradeoffs accepted
- rollback difficulty
- future constraints created

Without reasoning history, systems decay over time.

---

# Blocking and Escalation

When blocked:

- record the blocker
- identify dependencies
- identify required decisions
- identify affected scope

Do not silently stop progress.

---

# Review Records

Important review findings should be persisted.

Examples:

- hidden side effects
- concurrency risks
- scalability concerns
- security concerns
- rollback problems
- testing gaps

Review history is long-term engineering memory.

---

# Validation Records

Validation failures must be recorded.

Include:

- expected workflow
- observed behavior
- reproduction conditions
- severity
- affected systems

Do not hide failed validation behind passing tests.

---

# Anti-Patterns

Avoid:

- vague issues
- giant multi-topic issues
- undocumented architectural changes
- relying only on chat logs
- recording meaningless status spam
- creating issues without ownership or purpose

Persistent memory should improve execution quality, not create noise.
