# Autonomous Decision Policy

Agents should operate independently whenever safe.

Autonomy increases execution speed.
Unbounded autonomy increases system risk.

This document defines decision boundaries.

---

# Core Rule

Agents may make local, reversible, low-risk decisions.

Agents must escalate:

- destructive decisions
- irreversible decisions
- high-cost decisions
- security-sensitive decisions
- architecture-changing decisions

---

# Allowed Autonomous Decisions

Agents may decide independently:

- naming
- formatting
- local refactoring
- test additions
- internal cleanup
- comment improvements
- documentation improvements
- file organization
- small performance improvements
- implementation details inside approved architecture

These changes should remain:

- reversible
- low-risk
- scoped

---

# Disallowed Autonomous Decisions

Agents must not independently decide:

- breaking API changes
- destructive database changes
- production infrastructure changes
- security policy weakening
- authentication changes
- authorization model changes
- large dependency adoption
- external service integration
- large architecture migration
- billing-impacting behavior
- privacy-impacting behavior
- irreversible data transformations

These require explicit approval or escalation.

---

# Escalation Rules

Escalate when:

- requirements conflict
- architecture conflict exists
- evidence is insufficient
- the correct behavior is unclear
- risk exceeds confidence
- rollback is difficult

Escalation should include:

- current evidence
- proposed options
- risks
- tradeoffs
- recommended direction if possible

---

# Decision Logging

Important autonomous decisions should be recorded.

Record decisions when they affect:

- architecture
- public behavior
- compatibility
- deployment
- operational workflow
- long-term maintenance

Use:

- GitHub Issues
- ADRs
- architecture notes
- review records

---

# Parallel Work

When blocked by a decision:

- continue unrelated executable work
- reduce dependency chains
- isolate uncertainty

Do not stop the entire workflow unnecessarily.

---

# Uncertainty Rules

If uncertainty is high:

- reduce scope
- minimize impact
- avoid irreversible changes
- prefer safe defaults
- leave clear notes

Do not pretend certainty.

---

# Human Override

Explicit repository rules override autonomous decisions.

Human instructions override autonomous optimization.

Do not reinterpret explicit requirements into preferred behavior.

---

# Anti-Patterns

Avoid:

- rewriting architecture without approval
- hidden behavior changes
- unnecessary "improvements"
- speculative redesign
- changing APIs for elegance only
- optimization without measurement
- introducing systems nobody requested

Technical ambition is not automatically project value.
