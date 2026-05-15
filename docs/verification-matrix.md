# Verification Matrix

Verification depth should match system risk.

Not every change requires the same level of testing.

This matrix defines recommended verification coverage.

---

## Verification Types

| Verification Type | Purpose |
|---|---|
| Functional | Verify expected behavior |
| UI | Verify user interaction and layout |
| Performance | Verify latency, throughput, blocking behavior |
| Concurrency | Verify race conditions and synchronization |
| Recovery | Verify rollback and failure handling |
| Regression | Verify existing behavior remains stable |
| Security | Verify protection boundaries and sensitive behavior |
| Operational | Verify deployment and runtime stability |
| Validation | Verify real user workflow success |

---

# Verification Matrix

| Change Type | Functional | UI | Performance | Concurrency | Recovery | Regression | Security | Operational | Validation |
|---|---|---|---|---|---|---|---|---|---|
| Small internal refactor | Required | Optional | Optional | Optional | Optional | Required | Optional | Optional | Optional |
| Public API change | Required | Optional | Required | Optional | Required | Required | Required | Required | Required |
| UI workflow change | Required | Required | Optional | Optional | Optional | Required | Optional | Optional | Required |
| Background job change | Required | Optional | Required | Required | Required | Required | Optional | Required | Required |
| Database migration | Required | Optional | Optional | Optional | Required | Required | Required | Required | Required |
| Authentication change | Required | Optional | Optional | Optional | Required | Required | Required | Required | Required |
| Authorization change | Required | Optional | Optional | Optional | Required | Required | Required | Required | Required |
| Dependency upgrade | Required | Optional | Optional | Optional | Optional | Required | Required | Required | Optional |
| Infrastructure change | Required | Optional | Required | Optional | Required | Required | Required | Required | Required |
| Performance optimization | Required | Optional | Required | Optional | Optional | Required | Optional | Optional | Required |
| Concurrency change | Required | Optional | Required | Required | Required | Required | Optional | Required | Required |
| Recovery logic change | Required | Optional | Optional | Optional | Required | Required | Optional | Required | Required |
| Documentation-only change | Optional | Optional | Optional | Optional | Optional | Optional | Optional | Optional | Optional |

---

## Required Means Mandatory

Required means:

- verification should happen
- skipped verification must be justified
- missing verification must be reported

Do not silently skip required verification.

---

## Optional Means Risk-Based

Optional means:

- apply verification when risk justifies it
- apply verification when evidence is weak
- apply verification when system impact is unclear

Optional does not mean useless.

---

## Validation Priority

Validation has highest importance for:

- user-facing workflows
- operational workflows
- business-critical flows
- recovery workflows

Passing lower-level tests is insufficient when workflow validation fails.

---

## Concurrency Verification

Concurrency verification is required when changing:

- locking
- scheduling
- background workers
- async execution
- shared state
- retry systems
- queues
- event ordering

Concurrency bugs are often hidden in success-path tests.

---

## Recovery Verification

Recovery verification is required when changing:

- rollback behavior
- persistence
- migration
- retries
- state recovery
- failover
- cleanup logic

Recovery logic must be tested under failure conditions.

---

## Security Verification

Security verification is required when changing:

- authentication
- authorization
- secrets
- permissions
- external interfaces
- command execution
- file access
- dependency loading

Security-sensitive changes should assume hostile inputs.

---

## Operational Verification

Operational verification should include when relevant:

- startup
- deployment
- rollback
- monitoring
- logging
- observability
- upgrade safety
- restart behavior

Operational failures may not appear in development environments.

---

## Matrix Overrides

The matrix is a baseline.

Increase verification depth when:

- system risk is high
- uncertainty is high
- rollback is difficult
- blast radius is large
- production impact is large

Do not reduce verification depth only to move faster.

---

## Anti-Patterns

Avoid:

- identical verification depth for all tasks
- treating unit tests as full verification
- ignoring workflow validation
- ignoring concurrency risks
- skipping rollback verification
- reducing verification because the change seems simple

Verification strategy should match actual risk.
