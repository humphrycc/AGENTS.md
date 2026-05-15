# Done Criteria

Code compilation is not completion.

A task is complete only when the system behavior, validation state, and documentation state are acceptable.

---

# Required Completion Stages

A task is complete only after:

1. implementation
2. testing
3. review
4. validation
5. documentation update
6. risk reporting

Skipping stages creates hidden instability.

---

# Implementation Completion

Implementation is complete when:

- requested behavior exists
- affected flows work
- obvious edge cases are handled
- error handling exists
- rollback behavior is understood

Implementation alone is insufficient.

---

# Testing Completion

Testing is complete when relevant tests verify:

- success paths
- failure paths
- edge cases
- integration behavior
- concurrency behavior when relevant
- regression safety

Passing tests do not automatically prove the task objective.

---

# Review Completion

Review is complete when an independent review verifies:

- correctness
- maintainability
- scope control
- hidden side effects
- architecture consistency
- documentation impact
- test quality

Self-review alone is insufficient for non-trivial work.

---

# Validation Completion

Validation is complete when:

- the user requirement is actually satisfied
- the workflow behaves correctly
- operational expectations are met
- the system remains stable

Validation should simulate real usage whenever possible.

---

# Documentation Completion

Documentation is complete when affected:

- APIs
- workflows
- examples
- architecture notes
- operational procedures

are updated or explicitly marked as pending.

---

# Risk Reporting

Completion reports must include:

- remaining risks
- unverified areas
- assumptions made
- unresolved blockers
- future follow-up work

Do not present uncertainty as certainty.

---

# Partial Completion

Partial completion must be reported explicitly.

Examples:

- implementation finished, validation pending
- tests incomplete due to missing environment
- rollback unverified
- performance impact unknown

Do not label partial work as complete.

---

# Fake Completion Prevention

Never:

- claim tests passed when unverified
- claim validation happened when skipped
- hide known risks
- ignore failing checks silently
- mark work complete because time expired

Completion status must reflect reality.

---

# Long-Term Stability

Done criteria exist to preserve:

- maintainability
- reproducibility
- operational safety
- trust in automation
- trust in repository state

Fast completion without verification creates long-term instability.
