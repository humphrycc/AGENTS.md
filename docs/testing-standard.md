# Testing Standard

Tests must verify user reality, not only code execution.

The goal is confidence in behavior.

---

## Default Testing Standard

Use:

- stage closure testing
- complete user action testing
- regression testing
- failure-path testing

for all non-trivial work.

---

## Stage Closure Testing

Each development stage must have local verification.

Before a stage is considered closed:

- the changed behavior must be tested
- the failure path must be considered
- obvious edge cases must be checked
- regressions in nearby behavior must be checked

Do not stack multiple unverified stages.

---

## Complete User Action Testing

Tests should follow real user workflows.

A complete user action test should verify:

1. entry point
2. user interaction
3. state transition
4. expected output
5. persistence if relevant
6. refresh or reload behavior if relevant
7. error behavior
8. recovery behavior

Do not test only isolated functions while ignoring workflow behavior.

---

## Testing Perspectives

Testing should use multiple perspectives.

Recommended perspectives:

- functional behavior
- UI behavior
- performance behavior
- concurrency behavior
- operational behavior
- rollback behavior
- recovery behavior

Different perspectives detect different failures.

---

## Functional Testing

Functional tests verify:

- correct outputs
- valid state changes
- expected workflows
- edge cases
- invalid inputs
- permission behavior

Functional testing is mandatory.

---

## UI Testing

UI testing should verify:

- layout stability
- interaction correctness
- navigation
- responsive behavior
- visual regressions
- accessibility when relevant

A passing backend test does not prove usable UI behavior.

---

## Performance Testing

Performance testing should verify:

- latency
- blocking behavior
- memory growth
- concurrency stability
- throughput when relevant

Do not introduce blocking behavior in critical paths.

---

## Regression Testing

Regression testing verifies:

- existing workflows still work
- previous bugs do not reappear
- dependencies do not silently break behavior

Regression testing is required for shared systems.

---

## Failure-Path Testing

Failure behavior must be tested.

Verify:

- invalid input
- timeout behavior
- retry behavior
- cancellation behavior
- partial failure behavior
- rollback behavior
- corrupted state handling when relevant

Systems often fail in recovery paths, not success paths.

---

## Test Ownership

Testing should not rely only on the implementation perspective.

Recommended perspectives:

- coder
- tester
- reviewer
- validator

Independent testing improves reliability.

---

## Test Evidence

Test reports should include:

- tests run
- environment
- result
- skipped tests
- known gaps
- unresolved risks

Do not claim coverage without evidence.

---

## Testing Limits

If meaningful testing is impossible:

- explain why
- reduce uncertainty where possible
- isolate the risk
- document missing verification

Do not pretend the system was verified.

---

## Anti-Patterns

Avoid:

- testing only happy paths
- treating compilation as testing
- testing implementation details only
- fake test reports
- deleting failing tests
- ignoring workflow-level failures
- adding tests with weak assertions only for coverage metrics

Behavior confidence matters more than test quantity.
