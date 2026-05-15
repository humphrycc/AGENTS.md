# Development Standard

Agents must state the development standard before starting non-trivial implementation.

The standard defines how the work will be developed, closed, and verified.

---

## Default Standard: Stage Closure Development

Use stage closure development by default.

A task is divided into small stages.
Each stage must reach a stable checkpoint before the next stage starts.

A stage is closed only when:

- the intended change is implemented
- local behavior is checked
- obvious edge cases are considered
- relevant tests are added or updated
- known risks are recorded
- the next stage is clear

Do not let half-finished stages accumulate.

---

## Stage Design

Each stage should be:

- small
- testable
- reviewable
- reversible when possible
- tied to one clear objective

Avoid stages that mix:

- architecture changes
- feature behavior
- UI behavior
- test framework changes
- documentation rewrites

Split mixed work.

---

## Required Stage Record

For each non-trivial stage, record:

- stage goal
- files affected
- behavior changed
- tests added or run
- risks found
- open questions
- closure status

For long tasks, persist this in GitHub Issues.

---

## Development Standards to Declare

Before coding, declare:

- development standard
- testing standard
- review standard
- validation standard

Example:

```text
Development standard: stage closure development.
Testing standard: complete user action testing plus regression checks.
Review standard: independent reviewer perspective.
Validation standard: verify the full user workflow, not only unit behavior.
```

Do not start complex implementation without a stated standard.

---

## Local Closure

A local change is closed only when:

- the code compiles or syntax is valid
- the behavior is locally understood
- failure behavior is considered
- related tests exist or missing tests are justified
- no unrelated files were changed

Local closure does not equal task completion.

---

## Task Closure

A task is closed only when all stages are closed and final validation passes.

Task closure requires:

- implementation complete
- tests complete or limitations documented
- review complete
- validation complete
- documentation updated when needed
- risks listed

See `docs/done-criteria.md`.

---

## User Workflow First

Development should preserve user workflows.

When changing behavior, identify:

- user entry point
- user action sequence
- expected result
- failure result
- recovery path

Do not implement isolated code paths while ignoring the user workflow.

---

## No Open-Ended Development

Do not keep improving without a closure target.

Every development action should belong to:

- a stage
- a task
- a bug fix
- a validation failure
- a documented follow-up

Avoid vague continuous refinement.

---

## Stop Conditions

Stop or escalate when:

- requirements conflict
- source of truth conflicts
- security risk appears
- data loss risk appears
- rollback path is unclear
- tests cannot be meaningfully defined

If other safe work remains, continue that work.

---

## Anti-Patterns

Avoid:

- large unclosed implementation batches
- coding without declared standards
- finishing implementation before defining tests
- treating milestones as completion
- merging half-verified stages
- creating new work only to avoid stopping

Stable stage closure is more important than visible activity.
