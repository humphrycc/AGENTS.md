# Document Routing

Do not load all documents by default.

Read `AGENTS.md` first.
Then load only the documents needed for the current task.

The goal is targeted context, not maximum context.

---

## Default Loading Rule

Default behavior:

1. Read `AGENTS.md`.
2. Identify task type.
3. Load only relevant docs.
4. Ignore unrelated docs unless evidence points to them.

If unsure which document applies, read this file.

---

## Mandatory Standards

For non-trivial implementation tasks, also load:

- `docs/development-standard.md`
- `docs/testing-standard.md`

Before implementation, declare:

- development standard
- testing standard
- review standard
- validation standard

---

## Task Routing Table

| Task type | Read first | Optional follow-up |
|---|---|---|
| General coding | `docs/development-standard.md`, `docs/development-rules.md` | `docs/testing-standard.md`, `docs/done-criteria.md` |
| Bug fix | `docs/source-of-truth.md`, `docs/development-standard.md` | `docs/testing-standard.md`, `docs/workflow.md` |
| Test writing | `docs/testing-standard.md`, `docs/workflow.md` | `docs/multi-agent.md` |
| Code review | `docs/development-rules.md`, `docs/done-criteria.md` | `docs/verification-architecture.md` |
| UI validation | `docs/testing-standard.md`, `docs/workflow.md` | `docs/multi-agent.md` |
| Performance work | `docs/testing-standard.md`, `docs/development-rules.md` | `docs/verification-architecture.md` |
| Security-sensitive work | `docs/development-rules.md`, `docs/autonomous-decision-policy.md` | `docs/source-of-truth.md` |
| Documentation update | `docs/documentation.md`, `docs/source-of-truth.md` | `docs/done-criteria.md` |
| GitHub issue usage | `docs/github-issue-protocol.md` | `docs/source-of-truth.md` |
| Multi-agent coordination | `docs/multi-agent.md`, `docs/agent-lifecycle.md` | `docs/state-machine.md` |
| Agent lifecycle problem | `docs/agent-lifecycle.md`, `docs/state-machine.md` | `docs/multi-agent.md` |
| Autonomous decision | `docs/autonomous-decision-policy.md` | `docs/source-of-truth.md` |
| Completion check | `docs/done-criteria.md`, `docs/verification-architecture.md` | `docs/testing-standard.md` |
| Source conflict | `docs/source-of-truth.md` | `docs/documentation.md` |
| Failure recovery | `docs/failure-recovery.md` | `docs/state-machine.md` |
| Context handling | `docs/context-management.md` | `docs/document-routing.md` |

---

## Loading Limits

Prefer reading at most three detailed docs for a task.

Read more only when:

- the task spans multiple responsibilities
- evidence conflicts
- the agent is blocked
- the change is high-risk
- validation requires broader context

Do not read docs only because they exist.

---

## Priority Rules

When documents conflict:

1. `AGENTS.md` has highest priority.
2. Task-specific docs have next priority.
3. General docs have lower priority.
4. Old issues and chat history have lowest priority.

When docs conflict with source code, follow `docs/source-of-truth.md`.

---

## Context Budget Rules

Context is a limited resource.

Avoid loading:

- unrelated governance docs
- old discussions
- stale issues
- duplicate explanations
- broad architecture docs without need

Prefer precise evidence:

- specific files
- specific tests
- specific issues
- specific decisions

---

## When to Stop Reading

Stop loading documents when you have enough evidence to:

- define scope
- make a safe plan
- implement the task
- test the change
- validate completion

More reading is not automatically better.

---

## Anti-Patterns

Avoid:

- loading the full `docs/` directory by default
- treating all docs as equal priority
- using old docs to override current code
- reading broadly to avoid making a decision
- expanding context until the main task is lost

Document routing exists to keep agents focused.
