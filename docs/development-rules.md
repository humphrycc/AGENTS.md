# Development Rules

Development work must be small, traceable, and reversible.

The goal is stable progress.

---

## Default Behavior

Prefer:

- small changes
- isolated files
- existing patterns
- simple code
- explicit behavior
- readable names
- incremental verification

Avoid:

- large rewrites
- speculative abstraction
- unrelated refactoring
- hidden side effects
- premature optimization
- dependency churn

---

## Scope Control

Only change files required by the task.

Do not modify unrelated code because it looks imperfect.

If unrelated problems are found:

- record them
- create an issue if useful
- continue the current task

Do not expand task scope silently.

---

## Existing Patterns

Follow existing project patterns unless there is a clear reason not to.

Before introducing a new pattern, check:

- existing modules
- naming style
- error handling style
- test style
- logging style
- dependency usage

Consistency is usually more valuable than local elegance.

---

## Dependencies

Do not add dependencies casually.

Before adding a dependency, justify:

- why existing code is insufficient
- maintenance cost
- security risk
- license risk
- runtime cost
- replacement difficulty

Small utility code is often better than a new dependency.

---

## Refactoring

Refactoring is allowed when it directly supports the task.

Allowed refactoring:

- reduces duplication touched by the task
- makes the change safer
- improves testability
- fixes known design debt in the changed area

Disallowed refactoring:

- broad cleanup unrelated to the task
- renaming without value
- style-only rewrites across many files
- architecture changes without explicit need

---

## Error Handling

Do not suppress errors without understanding them.

Error handling must be:

- explicit
- observable when needed
- testable
- consistent with existing behavior

Avoid swallowing errors silently.

---

## Concurrency and Blocking

Do not introduce blocking behavior in main execution paths.

When adding concurrency:

- define ownership
- define cancellation
- define timeout behavior
- define cleanup behavior
- test failure paths

Avoid hidden deadlocks.

---

## Security

Treat security-sensitive changes as high risk.

High-risk areas include:

- authentication
- authorization
- secrets
- encryption
- network exposure
- file system access
- command execution
- dependency loading

Do not weaken security for convenience.

---

## Performance

Do not optimize blindly.

Before performance changes:

- identify the bottleneck
- measure when possible
- compare before and after
- preserve correctness

Never trade correctness for unproven performance gains.

---

## Backward Compatibility

Preserve compatibility unless the task explicitly allows breaking changes.

Breaking changes include:

- API changes
- behavior changes
- config format changes
- data format changes
- migration requirements

Breaking changes must be documented.

---

## Commit Hygiene

Commits should be logical and reviewable.

Each commit should explain:

- what changed
- why it changed

Do not mix unrelated changes in one commit.

---

## Forbidden Behavior

Never:

- delete tests to pass CI
- fake test results
- hide failing checks
- claim unverified work is verified
- overwrite user work without checking
- introduce unrelated behavior changes
