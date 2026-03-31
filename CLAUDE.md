# Exodus — Project Instructions
---
## Project Overview

exodus is a hebrew website for storybook of exodus 

---
## Workflow: Skill-First, Subagent-Driven (ENFORCED)

**Always use the best-matching skill for every task.** Check available skills before starting any work — if a skill applies, use it. This includes debugging (`superpowers:systematic-debugging`), code review (`superpowers:requesting-code-review`), planning (`superpowers:writing-plans`), and all other applicable skills.

**After analysis, execute via `superpowers:subagent-driven-development`.** Once you understand what needs to be done (via the appropriate skill), parallelize independent tasks across subagents for implementation. This is the default execution model for all feature work, bug fixes, and refactoring.

---
## TDD Methodology (ENFORCED)

**Every feature MUST be test-first.** No exceptions.

1. **First agent: write tests** — define expected behavior via failing tests
2. **Second agent: write implementation** — make the tests pass
3. **Never dispatch an implementation agent without its test agent completing first**

When dispatching parallel agents, dispatch test agents first, wait for completion, then implementation agents.

- Descriptive test names: `should return expired true when past expiry time`, not `testExpiry`
- **Before EVERY push, run tests locally.** Do NOT push and discover failures.
---

## GitHub Issue Tracking (ENFORCED)

Every new requirement, task, bug, or feature must be tracked as a GitHub issue. No exceptions.

1. **New work = new issue** — before starting any new feature, fix, or task, create a GitHub issue with clear acceptance criteria
2. **Close on completion** — when work is done and merged, close the issue with a reference to the commit or PR
3. **Labels** — use priority labels (`p0-mvp`, `p1-fast-follow`, `p2-roadmap`) and scope labels (`platform:mobile`, `platform:tv`, `platform:smart-tv`, `backend`, `ux`, `player`)
4. **Specs** — link to design specs in `docs/superpowers/specs/` when they exist
5. **Keep issues current** — if scope changes or work is superseded, update or close the issue
---
## Model Routing

Default subagents to the cheapest model that can handle the task:

| Task | Model | Examples |
|------|-------|---------|
| Explore / file search / counting | haiku | Codebase exploration, grep-like searches, file inventory |
| Read-only research / data gathering | haiku | Reading files, summarizing, extracting patterns |
| Git operations | haiku | Status, add, commit, push, log, branch, diff, merge |
| Test writing | haiku | Writing tests from existing patterns, adding coverage, fixture setup |
| Boilerplate / config edits | haiku | README updates, .gitignore, config files, package.json tweaks |
| Test failure diagnosis / fix | sonnet | Debugging failing tests, fixing mock paths, resolving import issues |
| Research + plan (hybrid) | sonnet | Reading code then producing a plan, summarizing + recommending |
| Code editing / implementation | sonnet | Writing code, editing files, running tests |
| Architecture / planning / synthesis | opus | Design decisions, cross-cutting analysis, complex refactors |
