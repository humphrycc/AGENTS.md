# Verification Architecture

Verification exists to prevent false confidence.

Code execution alone is not proof of correctness.

Verification must use multiple perspectives.

---

## Verification Layers

Recommended layers:

1. implementation verification
2. test verification
3. review verification
4. behavioral validation
5. operational verification

Different layers detect different failures.

---

## Implementation Verification

Checks:

- requested behavior exists
- implementation matches scope
- obvious logic errors are absent
- error handling exists
- rollback behavior is reasonable

Implementation verification is local.

It does not prove user success.

---

## Test Verification

Tests should verify:

- success paths
- failure paths
- edge cases
- concurrency behavior
- regression safety
- integration behavior

Tests should validate behavior, not only code coverage.

High coverage with weak assertions is low-quality verification.

---

## Review Verification

Review should verify:

- correctness
- maintainability
- architecture consistency
- hidden side effects
- scope control
- documentation impact
- risk visibility

Independent review is critical.

Self-confirmation is unreliable.

---

## Behavioral Validation

Behavioral validation checks:

- user workflow success
- operational usability
- expected system interaction
- real-world task completion

A feature can pass tests and still fail validation.

---

## Operational Verification

Operational verification checks:

- deployment safety
- rollback safety
- monitoring visibility
- recovery behavior
- upgrade safety
- production stability

Operational failures are often invisible in unit tests.

---

## Evidence Hierarchy

Verification evidence priority:

1. observed runtime behavior
2. reproducible validation
3. tests
4. review
5. assumptions

Assumptions are weak evidence.

---

## Conflict Resolution

When verification sources disagree:

### Code passes tests but fails validation

Validation wins.

### Documentation disagrees with behavior

Follow `source-of-truth.md`.

### Review disagrees with implementation

Re-investigate before merging.

### Old assumptions disagree with current runtime behavior

Runtime behavior wins until disproven.

---

## Verification Ownership

Verification should use different perspectives.

Recommended separation:

- implementer
- tester
- reviewer
- validator

Do not rely entirely on one agent perspective.

---

## Verification Reporting

Verification reports should include:

- what was verified
- how it was verified
- what was not verified
- remaining uncertainty
- known risks

Do not hide missing verification.

---

## Fake Verification Prevention

Never:

- claim tests ran when they did not
- claim validation happened when skipped
- treat compilation as correctness
- treat code review as runtime proof
- hide failing checks

Verification must reflect reality.

---

## Verification Depth

Verification depth should match risk.

Higher-risk changes require:

- broader testing
- independent review
- operational validation
- rollback planning

Low-risk changes may use lighter verification.

Verification cost should scale with impact.
