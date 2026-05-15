# AGENTS.md

This file defines the default operating rules for AI coding agents in this repository.

Keep this file short. Put detailed rules in `docs/`.

---

## Communication

- Be direct.
- Use short sentences.
- Avoid filler.
- Avoid motivational language.
- Avoid the sentence pattern "not A, but B".
- Give conclusions first.
- State uncertainty clearly.

---

## Source of Truth

All factual decisions must be based on repository evidence.

Priority order:

1. Current source code
2. Repository documentation
3. Tests
4. GitHub issues and pull requests
5. Chat history

Chat history is context only.
Chat history is never the source of truth.

If code conflicts with documentation:

- Treat code as current behavior.
- Treat documentation as intended behavior.
- Record the conflict in GitHub Issues.
- Fix the conflict if the task scope allows it.

Do not invent behavior from assumptions.

See: `docs/source-of-truth.md`

---

## Workflow

For non-trivial tasks, follow this order:

1. Investigate
2. Plan
3. Implement
4. Test
5. Review
6. Validate
7. Document

Do not skip planning.
Do not guess when requirements are unclear.

If blocked:

- Ask for clarification only when necessary.
- Continue independent work that does not depend on the blocked decision.
- Record the blocker in GitHub Issues when useful.

See: `docs/workflow.md`

---

## Multi-Agent Rules

Use single responsibility for agent work.

Separate responsibilities:

- coding
- functional testing
- UI testing
- performance testing
- security review
- code review
- documentation
- final validation

The same agent should not implement, test, review, and validate the same change alone.

Testing must be reviewed by coder, tester, and reviewer perspectives.

See: `docs/multi-agent.md`

---

## Runtime and Agent Lifecycle

The main thread must not call blocking operations directly.

If agents fail, hang, or exceed useful limits:

- clean unused agents
- clean stuck agents
- retry safely
- wait only when waiting has clear value

Do not spawn agents without bounds.
Do not create fake work to appear active.
Do not treat milestones as stopping points if executable work remains.

See: `docs/agent-lifecycle.md`

---

## Development Rules

Prefer:

- small changes
- isolated files
- existing patterns
- incremental verification
- clear rollback paths

Avoid:

- unrelated refactoring
- speculative abstraction
- hidden side effects
- new dependencies without reason
- rewriting working logic without need

Never delete tests to make CI pass.
Never hide failures.
Never fake completion.

See: `docs/development-rules.md`

---

## Documentation Rules

Documentation must remain accurate.

After changes, update affected:

- README files
- API documents
- architecture notes
- examples
- operation guides

If documentation is outdated, fix it or create an issue.

See: `docs/documentation.md`

---

## GitHub Issue Protocol

Use GitHub Issues to persist meaningful development records.

Record:

- plans
- progress
- blockers
- architectural decisions
- agent coordination
- bugs
- review notes
- validation reports

Do not rely only on chat context for project memory.

See: `docs/github-issue-protocol.md`

---

## Autonomous Decision Policy

Agents should complete work independently when safe.

Allowed autonomous decisions:

- naming
- formatting
- local refactoring
- non-breaking cleanup
- test improvements
- internal organization

Disallowed autonomous decisions:

- breaking API changes
- destructive data changes
- security policy changes
- production infrastructure changes
- large dependency changes
- cost-impacting decisions
- external service adoption

If a disallowed decision is required, mark it as blocked and continue other work.

See: `docs/autonomous-decision-policy.md`

---

## Done Criteria

A task is complete only when:

- implementation is finished
- relevant tests pass or failures are explained
- independent review is complete
- validation is complete
- affected documentation is updated
- risks are listed
- unverified areas are listed

Final reports must include:

- what changed
- tests run
- review result
- validation result
- risks
- follow-up work

See: `docs/done-criteria.md`
