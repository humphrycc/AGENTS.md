# Documentation Rules

Documentation is part of the system.

Outdated documentation creates hidden failures.

---

# Core Principles

Documentation must be:

- accurate
- current
- traceable
- scoped
- maintainable

Documentation should describe reality.

Do not write aspirational fiction.

---

# Documentation Responsibilities

After changing behavior, update affected documentation.

Possible updates include:

- README files
- API documentation
- architecture notes
- deployment guides
- operational guides
- examples
- migration guides
- troubleshooting notes

Code changes and documentation changes should stay synchronized.

---

# Architecture Documentation

Architecture documentation should explain:

- system boundaries
- responsibilities
- dependencies
- data flow
- failure handling
- concurrency model
- scaling assumptions
- operational constraints

Architecture documents should explain why decisions exist.

---

# Operational Documentation

Operational documentation should include:

- startup steps
- deployment steps
- rollback steps
- failure recovery
- debugging guidance
- monitoring expectations
- dependency requirements

Operational procedures should be reproducible.

---

# Example Quality

Examples must work.

Do not leave:

- stale commands
- invalid APIs
- pseudo-code pretending to be real
- outdated screenshots
- broken workflows

Broken examples destroy trust.

---

# Documentation vs Code

If documentation conflicts with code:

- identify the conflict
- determine intended behavior
- update documentation or code
- record unresolved conflicts

Do not silently ignore mismatches.

---

# Change Tracking

Major changes should include:

- migration notes
- compatibility impact
- operational impact
- rollback impact

Future maintainers should understand:

- what changed
- why it changed
- what risks were accepted

---

# AI-Generated Documentation

AI-generated documentation must be verified.

Do not assume generated content is accurate.

Verify:

- commands
- file paths
- APIs
- workflows
- configuration examples
- environment assumptions

Generated text without verification is unsafe.

---

# Anti-Patterns

Avoid:

- duplicate documentation without ownership
- giant monolithic documents
- stale TODO lists
- undocumented breaking changes
- architecture diagrams without explanations
- copying code comments into docs without context

Documentation should reduce ambiguity, not create it.
