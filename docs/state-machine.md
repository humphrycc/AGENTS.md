# Agent State Machine

Agent work must have explicit states.

Unclear states cause:

- fake progress
- duplicated ownership
- retry loops
- deadlocks
- unfinished validation
- unclear completion

---

## Standard States

Use these states for non-trivial agent workflows:

1. `CREATED`
2. `INVESTIGATING`
3. `PLANNING`
4. `IMPLEMENTING`
5. `TESTING`
6. `REVIEWING`
7. `VALIDATING`
8. `DOCUMENTING`
9. `COMPLETED`

Exceptional states:

- `BLOCKED`
- `WAITING`
- `FAILED`
- `CANCELLED`
- `ESCALATED`

---

## State Meanings

### CREATED

The task exists but no meaningful work has started.

Required output:

- task owner
- task objective
- initial scope

### INVESTIGATING

The agent is collecting evidence.

Required output:

- files inspected
- docs inspected
- issues inspected when useful
- current behavior summary

### PLANNING

The agent is deciding how to act.

Required output:

- planned changes
- affected files
- risks
- testing approach
- unresolved questions

### IMPLEMENTING

The agent is changing code or documents.

Required output:

- changed files
- behavior changed
- assumptions made

### TESTING

The agent is checking behavior with tests.

Required output:

- tests run
- test result
- failures
- skipped checks

### REVIEWING

An independent review checks the work.

Required output:

- review findings
- required fixes
- accepted risks

### VALIDATING

The agent verifies task-level success.

Required output:

- requirement satisfied or not
- workflow verified or not
- remaining uncertainty

### DOCUMENTING

The agent updates project memory.

Required output:

- docs updated
- issues updated
- decisions recorded

### COMPLETED

All required done criteria are satisfied.

Required output:

- final summary
- tests
- review result
- validation result
- risks
- follow-up work

---

## Exceptional States

### BLOCKED

Work cannot safely continue without missing input or dependency resolution.

Required output:

- blocker
- needed decision
- safe parallel work

### WAITING

Work is waiting for another active process.

Required output:

- what is being waited on
- why waiting is useful
- timeout or retry condition

### FAILED

The task failed.

Required output:

- failure reason
- impact
- recovery option
- next safe action

### CANCELLED

The task is intentionally stopped.

Required output:

- reason
- partial changes
- cleanup result

### ESCALATED

The task requires higher-level decision.

Required output:

- decision required
- options
- tradeoffs
- recommendation if available

---

## Transition Rules

Allowed normal path:

```text
CREATED
→ INVESTIGATING
→ PLANNING
→ IMPLEMENTING
→ TESTING
→ REVIEWING
→ VALIDATING
→ DOCUMENTING
→ COMPLETED
```

Allowed exception paths:

```text
ANY → BLOCKED
ANY → FAILED
ANY → CANCELLED
ANY → ESCALATED
WAITING → previous active state
BLOCKED → PLANNING
FAILED → PLANNING or CANCELLED
```

Do not jump from `IMPLEMENTING` directly to `COMPLETED`.

---

## Ownership Rules

Every active task needs one owner.

Every verification stage needs a different perspective when possible.

Ownership must be clear for:

- implementation
- testing
- review
- validation
- documentation

No task should be owned by everyone.

---

## Retry Rules

Retries must return to `PLANNING` unless the failure is purely transient.

Before retrying:

- explain the failure
- adjust the plan
- reduce scope if useful
- avoid repeating the same failed action

---

## Completion Guard

A task cannot reach `COMPLETED` unless:

- implementation is done
- tests are run or explicitly impossible
- review is complete
- validation is complete
- documentation is updated or explicitly not needed
- risks are reported

`COMPLETED` is a verified state, not a mood.
