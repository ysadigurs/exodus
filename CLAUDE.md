# Exodus — Project Instructions
---
## Project Overview

**Exodus Adventure** is an interactive Hebrew-language (RTL) children's storybook web app that retells the biblical Book of Exodus across 5 sequential chapters:

1. **יעקב מגיע למצרים** — Jacob arrives in Egypt and reunites with Joseph
2. **בני ישראל במצרים: השעבוד** — Life under slavery in Egypt
3. **משה והסנה הבוער** — Moses and the burning bush
4. **עשר המכות** — The ten plagues
5. **קריעת ים סוף** — Crossing the Red Sea

### Target Audience
Children ages 5–12.

### Tech Stack
- **Static HTML pages** — each chapter is a standalone `code.html` file in `exodus_src/`
- **Tailwind CSS** (CDN) with a custom Material Design 3–inspired color theme ("Nile-to-Desert" warm palette)
- **Google Fonts** — Plus Jakarta Sans (headlines), Be Vietnam Pro (body)
- **Google Material Symbols** for iconography

### Design System ("The Wandering Storyteller")
Defined in `exodus_src/eden_adventure/DESIGN.md`. Key principles:
- **"Digital Pop-Up Book"** aesthetic — organic asymmetry, overlapping elements, tonal layering instead of borders
- **Warm palette** — Ancient Gold primary (#775600), Sky & Water secondary (#005f9c), Nile Green tertiary (#006b1b), cream background (#fdf7df)
- **Tactile components** — 3D "pressable stone" buttons with bottom-offset shadows, papyrus-style cards, no hard borders
- **No pure black** — all dark text uses `#312f1f`

### Page Structure (per chapter)
Each chapter page includes:
- **Top app bar** — sticky header with "Exodus Adventure" title, map icon, back navigation
- **Hero section** — illustration + chapter title + narrative intro
- **Video placeholder** — play button over a cinematic thumbnail
- **Trivia/quiz section** — multiple-choice questions about the chapter's story
- **Progress indicator** — shows current chapter (1–5)
- **Bottom nav bar** — Previous / Progress / Next navigation with glassmorphism effect

### Additional Materials
- Each chapter directory contains a `screen.png` screenshot alongside its `code.html`
- `eden_adventure/` holds the design system documentation

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
