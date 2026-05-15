# Source of Truth

Agents must make factual decisions from repository evidence.

Chat history can explain intent. It cannot override repository evidence.

---

## Priority Order

Use this order when deciding facts:

1. Current source code
2. Repository documentation
3. Tests
4. GitHub issues and pull requests
5. Chat history

Higher priority evidence wins.

---

## Code vs Documentation

When code and documentation disagree:

- Code represents current behavior.
- Documentation represents intended or historical behavior.
- The conflict must be recorded.
- The agent should fix the conflict if it is within task scope.
- If the correct direction is unclear, create or update an issue.

Do not silently choose one side and hide the conflict.

---

## Tests as Evidence

Tests describe expected behavior only when they are consistent with code and documentation.

If tests conflict with both code and docs:

- Treat them as stale or incomplete until verified.
- Record the mismatch.
- Do not delete tests only to pass CI.

If a failing test exposes a real bug, fix the bug.
If a failing test is obsolete, update the test and explain why.

---

## GitHub Issues and PRs

Issues and PRs are project memory.

Use them to understand:

- why a decision was made
- what tradeoffs were accepted
- which behavior is planned
- which problems are known

Old issues may be stale. Verify against current code before acting.

---

## Chat History

Chat history is useful for:

- user preference
- task intent
- project direction
- unresolved discussion

Chat history is not enough for:

- API behavior
- architecture decisions
- current implementation
- release state
- test expectations

If chat history says one thing and the repo says another, trust the repo and record the mismatch.

---

## Evidence Requirements

Before changing behavior, identify at least one evidence source:

- file path
- test name
- issue link
- PR link
- documented requirement

If no evidence exists, state the assumption clearly and keep the change minimal.

---

## No Invention Rule

Do not invent:

- undocumented APIs
- hidden requirements
- unsupported behaviors
- imaginary user decisions
- non-existent architecture rules

If information is missing, mark it as missing.
