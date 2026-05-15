# Multi-Agent Architecture

Use single responsibility principle for agents.

Avoid large agents that simultaneously:

- implement
- test
- review
- validate
- approve

This creates blind spots and fake confidence.

---

# Agent Responsibilities

Separate responsibilities whenever possible.

Recommended agent types:

- implementation agent
- functional testing agent
- UI testing agent
- performance testing agent
- regression testing agent
- security review agent
- architecture review agent
- documentation agent
- validation agent

One agent may coordinate.
One agent should not own the full lifecycle alone.

---

# Independent Review

Review agents must not blindly trust implementation output.

Review responsibilities:

- inspect logic
- inspect side effects
- inspect rollback safety
- inspect test completeness
- inspect hidden assumptions
- inspect architectural consistency

Review must include disagreement when appropriate.

---

# Testing Separation

Different testing perspectives catch different failures.

Functional testing verifies:

- feature correctness
- expected outputs
- edge behavior

UI testing verifies:

- layout
- interaction
- accessibility
- visual regressions

Performance testing verifies:

- latency
- throughput
- memory usage
- blocking behavior

Regression testing verifies:

- previous behavior stability
- compatibility
- dependency impact

---

# Validation

Validation is the final behavioral confirmation.

Validation checks:

- the user requirement is actually satisfied
- the workflow is usable
- the system remains stable
- no major hidden regressions exist

Validation is not the same as unit testing.

---

# Coordination Rules

Multi-agent coordination must be explicit.

Agents should:

- define ownership clearly
- define outputs clearly
- define dependencies clearly
- define completion criteria clearly

Avoid:

- duplicated ownership
- hidden dependencies
- circular delegation
- recursive delegation loops

---

# Communication Persistence

Important coordination must be persisted.

Use GitHub Issues or repository documents for:

- architecture decisions
- blockers
- task ownership
- unresolved risks
- validation reports
- major review findings

Do not rely only on runtime context.

---

# Escalation

Escalate only when:

- requirements conflict
- architecture conflict exists
- security risk exists
- destructive changes are required
- uncertainty cannot be reduced safely

Do not escalate trivial decisions.

---

# Anti-Pattern Rules

Avoid:

- infinite agent spawning
- fake parallelism
- unnecessary delegation
- agents reviewing their own assumptions only
- using more agents without increasing verification quality

More agents do not automatically improve reliability.
