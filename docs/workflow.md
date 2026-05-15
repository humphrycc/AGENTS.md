# Workflow

All non-trivial work must follow a structured workflow.

Skipping stages creates instability, hidden regressions, and fake completion.

---

# Standard Workflow

1. Investigate
2. Plan
3. Implement
4. Test
5. Review
6. Validate
7. Document

Do not skip directly from implementation to completion.

---

# Investigation

Before implementation:

- inspect related code
- inspect tests
- inspect architecture documents
- inspect existing patterns
- inspect recent issues and PRs if useful

Understand:

- current behavior
- intended behavior
- constraints
- dependencies
- rollback impact

Do not start coding from assumptions.

---

# Planning

For non-trivial tasks, produce a plan before implementation.

The plan should include:

- scope
- affected files
- risks
- testing strategy
- rollback strategy
- unresolved questions

Plans should be small and executable.

Avoid large speculative rewrites.

---

# Implementation

Implementation rules:

- keep changes isolated
- prefer incremental changes
- preserve existing patterns
- minimize side effects
- maintain backward compatibility unless explicitly changing behavior

Avoid:

- broad refactors
- unrelated cleanup
- hidden behavior changes
- speculative abstractions

---

# Testing

Every behavior change requires testing.

Testing should include when applicable:

- success paths
- failure paths
- edge cases
- concurrency risks
- rollback behavior
- integration behavior
- performance impact

Tests must verify behavior, not only code execution.

---

# Review

Review must be independent from implementation.

Review should check:

- correctness
- scope control
- maintainability
- architecture consistency
- test quality
- documentation impact
- hidden regressions

Reviewers should challenge assumptions.

---

# Validation

Validation is separate from testing.

Validation checks:

- the task objective was actually achieved
- the user requirement was satisfied
- the behavior matches the intended workflow
- the system remains stable

Passing tests alone is insufficient.

---

# Documentation

After implementation:

- update relevant documentation
- update examples
- update architecture notes if needed
- update operational guidance

Do not leave stale examples.

---

# Blocking Rules

If blocked:

- identify the blocker clearly
- reduce uncertainty if possible
- continue unrelated executable work
- record the blocker when useful

Do not guess.

Do not fabricate decisions.

---

# Completion Rules

A task is complete only after:

- implementation
- testing
- review
- validation
- documentation

Milestones are checkpoints.

Milestones are not completion states.
