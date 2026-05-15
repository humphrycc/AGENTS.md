# Task Protocol

Agent work must use explicit task protocols.

A task protocol defines:

- input
- output
- ownership
- handoff
- review
- validation
- escalation

Without a protocol, agents rely on memory and assumptions.

---

## Task Input Schema

Every non-trivial task should define:

```text
Task ID:
Task title:
Objective:
Source of truth:
Scope:
Out of scope:
Constraints:
Risks:
Required standards:
Expected output:
```

Required standards should include:

- development standard
- testing standard
- review standard
- validation standard

---

## Task Output Schema

Every non-trivial task should output:

```text
Task ID:
Status:
Summary:
Files changed:
Behavior changed:
Tests run:
Review result:
Validation result:
Documentation updated:
Risks:
Unverified areas:
Follow-up work:
```

Do not omit risks or unverified areas.

---

## Handoff Schema

When one agent hands work to another, include:

```text
From:
To:
Task ID:
Current state:
Completed work:
Remaining work:
Relevant files:
Relevant docs:
Known risks:
Open questions:
Expected next action:
```

A handoff without state is unsafe.

---

## Review Schema

Review output should include:

```text
Reviewer:
Scope reviewed:
Findings:
Required fixes:
Optional suggestions:
Risks:
Decision:
```

Allowed decisions:

- approve
- approve with risks
- request changes
- block

Review must distinguish required fixes from optional suggestions.

---

## Validation Schema

Validation output should include:

```text
Validator:
User workflow tested:
Expected behavior:
Observed behavior:
Result:
Unverified areas:
Risks:
Decision:
```

Allowed decisions:

- validated
- validated with risks
- failed
- blocked

Validation must focus on real behavior, not only internal implementation.

---

## Escalation Schema

Escalation output should include:

```text
Escalation reason:
Decision required:
Options:
Tradeoffs:
Recommendation:
Impact if delayed:
Safe work that can continue:
```

Escalation should be concise and decision-oriented.

---

## Blocker Schema

Blockers should include:

```text
Blocker:
Why it blocks:
Evidence:
Needed input:
Temporary workaround:
Safe parallel work:
```

Do not mark a task blocked without explaining what can still continue.

---

## Progress Record Schema

For long-running tasks, record progress as:

```text
Stage:
State:
Completed:
Current focus:
Next action:
Risks:
Blockers:
```

Use GitHub Issues when progress matters beyond the current execution context.

---

## Protocol Rules

- Use schemas for non-trivial work.
- Keep schemas concise.
- Do not fill fields with vague text.
- Prefer evidence over confidence language.
- Record uncertainty explicitly.

---

## Anti-Patterns

Avoid:

- vague handoffs
- missing ownership
- missing state
- hidden blockers
- undocumented risk transfer
- validation without expected behavior
- review without decision

A protocol is useful only when it reduces ambiguity.
