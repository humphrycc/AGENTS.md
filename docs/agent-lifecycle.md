# Agent Lifecycle

Agents are resources.

Poor lifecycle management causes:

- deadlocks
- runaway recursion
- context pollution
- fake activity
- unstable orchestration
- resource exhaustion

Lifecycle management is mandatory.

---

# Agent States

Recommended states:

- created
- investigating
- planning
- implementing
- testing
- reviewing
- validating
- blocked
- waiting
- completed
- cancelled
- failed

State transitions should be explicit.

---

# Main Thread Rules

The main coordination thread must avoid blocking operations.

The coordinator should:

- monitor progress
- manage dependencies
- manage retries
- manage escalation
- manage cleanup

Long-running work should be delegated.

---

# Blocking Rules

If blocked:

- identify the blocker
- identify dependency owners
- continue independent work if possible
- avoid idle waiting loops

Do not infinitely retry without new information.

---

# Waiting Rules

Waiting is acceptable only when:

- another task is actively progressing
- a dependency is expected
- waiting is cheaper than restarting

Waiting is not acceptable as fake activity.

---

# Failure Handling

On failure:

1. identify root cause
2. isolate impact
3. retry safely if appropriate
4. document the failure
5. escalate if necessary

Do not hide failures.
Do not silently continue after corruption.

---

# Retry Rules

Retries must be bounded.

Repeated failure without new information is waste.

Before retrying:

- identify why the previous attempt failed
- change conditions if possible
- reduce scope if useful

Do not retry infinitely.

---

# Agent Cleanup

Unused or stuck agents should be cleaned.

Cleanup candidates:

- deadlocked agents
- idle agents
- duplicate agents
- orphaned agents
- stale retry loops

Resource cleanup is part of orchestration.

---

# Recursion Rules

Recursive delegation must be bounded.

Every recursive workflow should define:

- depth limits
- termination conditions
- ownership transfer
- rollback behavior

Do not create self-expanding recursive systems.

---

# Resource Budgeting

Agent creation should consider:

- task value
- complexity
- verification value
- available context budget
- runtime cost

Do not increase agents without measurable benefit.

---

# Fake Completion Prevention

Agents must not:

- fabricate success
- fabricate progress
- fabricate verification
- create meaningless subtasks
- endlessly refine without value

If no executable work remains:

- enter waiting state
- report blockers
- report risks
- stop generating fake activity
