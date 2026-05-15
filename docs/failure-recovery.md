# Failure Recovery

Failures are normal.

Unrecoverable systems are unstable systems.

Recovery behavior must be designed explicitly.

---

## Core Goals

Recovery systems should:

- isolate failures
- preserve useful progress
- reduce cascading damage
- restore stable execution
- maintain observability

The goal is controlled recovery, not pretending failure never happened.

---

## Failure Categories

### Local Failure

Limited impact.

Examples:

- test failure
- single agent crash
- isolated validation failure
- temporary dependency issue

Preferred action:

- isolate
- retry safely
- continue unaffected work

---

### Systemic Failure

Broad impact.

Examples:

- corrupted architecture assumptions
- widespread regression
- orchestration deadlock
- invalid repository state
- broken deployment process

Preferred action:

- stop unsafe execution
- reduce scope
- re-evaluate assumptions
- escalate if needed

---

## Recovery Stages

Recommended recovery process:

1. detect
2. isolate
3. analyze
4. recover
5. verify
6. document

Skipping analysis causes repeated failure.

---

## Detection

Failures should be observable.

Detection sources include:

- tests
- logs
- validation
- monitoring
- review findings
- runtime behavior

Silent failure is dangerous.

---

## Isolation

Before recovery:

- identify affected systems
- identify unsafe assumptions
- prevent cascading impact
- preserve unaffected work

Do not expand damage during recovery.

---

## Retry Rules

Retries should be bounded.

Before retrying:

- identify failure reason
- determine whether retry conditions changed
- reduce scope if useful
- avoid repeating identical failure loops

Retries without learning are waste.

---

## Rollback

Rollback should be possible for high-risk work.

Rollback planning should consider:

- changed files
- data impact
- migration impact
- deployment impact
- compatibility impact

Rollback procedures should be documented.

---

## Partial Recovery

Partial recovery is acceptable.

Examples:

- disable unstable feature
- isolate failing subsystem
- preserve read-only functionality
- continue unaffected workflows

Stable partial functionality is better than unstable total failure.

---

## Recovery Verification

After recovery:

- verify system stability
- verify rollback correctness
- verify operational behavior
- verify monitoring visibility

Recovery is incomplete without verification.

---

## Failure Documentation

Important failures should be recorded.

Record:

- root cause
- impact
- timeline
- recovery action
- remaining risks
- prevention strategy

Failure history improves long-term reliability.

---

## Escalation

Escalate when:

- recovery risk is high
- rollback risk is high
- security is affected
- data integrity is uncertain
- production stability is uncertain

Do not hide systemic instability.

---

## Anti-Patterns

Avoid:

- infinite retries
- silent rollback
- ignoring corrupted state
- hiding failures to appear stable
- restarting without diagnosis
- continuing unsafe execution
- claiming recovery without verification

Recovery quality matters more than recovery speed.
