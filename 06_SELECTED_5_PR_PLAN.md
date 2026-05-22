# 06_SELECTED_5_PR_PLAN.md — directional-prompting

## Selected PR Candidates

From 05_PR_CANDIDATES.md, the following 5 PRs are selected for execution. These are ordered by priority and cover documentation, community health, and content quality improvements.

---

## PR 1: Add CONTRIBUTING.md

**File to create:** `CONTRIBUTING.md`

**Summary:** Add a contributing guide that explains how the community can engage with the directional-prompting repo.

**Change:**
```markdown
# Contributing to Directional Prompting

## What this repo is

directional-prompting is a documentation/methodology repository. The "product" is SKILL.md — a skill definition that teaches the outcome-first + directional-language pattern for writing prompts and agent directives.

## How to contribute

### Reporting issues

Use GitHub Issues to report:
- Bugs in the SKILL.md methodology (an example that doesn't work as described)
- Broken links or unclear instructions in README.md
- Missing agent compatibility

### Suggesting improvements

The best improvements come with a before/after rewrite demonstrating the fix. Follow the skill's own rules: open with the outcome block (goal, success means, stop when), then make every sentence lead with a positive verb.

### Pull requests

- Keep PRs small and focused
- Validate that any rewrite you propose follows the outcome + directional pattern
- No code changes — this repo has no runtime

## Philosophy

The directional prompting methodology is: **open with the destination, name the path with positive verbs, make the correct behavior the only behavior described.**

Every contribution to this repo should model that principle.

## License

MIT. By contributing, you agree that your contributions will be licensed under the MIT License.
```

---

## PR 2: Add CODE_OF_CONDUCT.md

**File to create:** `CODE_OF_CONDUCT.md`

**Summary:** Standard Contributor Covenant 2.1 code of conduct.

**Change:** Add Contributor Covenant 2.1 template from https://www.contributor-covenant.org/version/2/1/code_of_conduct/

---

## PR 3: Add More SKILL.md Examples

**File to modify:** `plugins/directional-prompting/skills/directional-prompting/SKILL.md`

**Summary:** Add two additional before/after rewrite examples to make the methodology more accessible.

**Changes:** After the existing code reviewer example (lines 100-129), add:

```
## Example 2 — System prompt for a file-editing agent

**Before** (no outcome, negatives throughout):

```
You are a file editor. Don't make arbitrary changes. Don't touch files
unless asked. Avoid introducing bugs. Don't refactor unless the user
explicitly asks for it. Be careful with large files.
```

**After** (outcome on top, directional inside):

```
Goal: Edit files as instructed and return a summary of changes made.

Success means:
  - Each edit is applied to the exact file and line range specified
  - Summary lists every file changed and what changed in each

Stop when: All requested edits are applied and a summary is returned.

Read the file before editing. Apply the change precisely.
Return a line-by-line summary of every edit made.
```

**Example 3 — Skill description for a "test writing" skill

**Before** (negative-heavy, no outcome):

```
Don't write flaky tests. Avoid using `sleep` or `waitFor` unless
necessary. Don't mock everything — prefer integration tests.
Don't skip edge cases. Avoid testing implementation details.
```

**After** (outcome + directional):

```
Goal: Write test suites that verify correctness and catch regressions.

Success means:
  - Every test is deterministic (no flakiness)
  - Tests cover the happy path and the top three edge cases
  - No `sleep` or `waitFor` unless the test genuinely needs async settling

Stop when: All tests pass and the coverage report shows >80% branch coverage.

Write tests that call the real function. Assert on returned values.
Cover edge cases by parameterizing with boundary values.
Use `waitFor` only when the framework requires it.
```
```

---

## PR 4: Verify and Update External Links

**File to modify:** `README.md`

**Summary:** Verify the OpenAI Codex Skills external link is current.

**Changes:**
- Confirm `https://developers.openai.com/codex/skills` is the correct URL for the Agent Skills standard
- If the URL has changed, update to the current URL
- If the page has moved but no equivalent exists, note that the link is informational

(Note: This may be a no-op if the link is still valid, but it demonstrates proactive maintenance.)

---

## PR 5: Clarify Cursor Install Path in README

**File to modify:** `README.md`

**Summary:** The compatibility table mentions Cursor rules at `.cursor/skills/directional-prompting/` but the Install section does not cover Cursor. Add a brief note.

**Changes:** After the Codex CLI install section (after line 88), add:

```
### Cursor

Place the skill at `.cursor/skills/directional-prompting/SKILL.md` in your project directory. Cursor scans this path for skill discovery.

### General

The skill works in any agent that reads `SKILL.md` from a skills directory. If your agent is not listed above, place the `directional-prompting/` directory (containing `SKILL.md`) in your agent's skills directory and consult the agent's documentation.
```

---

## Execution Order

1. `CONTRIBUTING.md` — creation, no modification risk
2. `CODE_OF_CONDUCT.md` — creation, no modification risk
3. `SKILL.md` — targeted addition only (adding examples after existing example, no existing content modified)
4. `README.md` — targeted additions (link verification + Cursor note), minimal touch

## Risk Assessment

| PR | Files Touched | Risk | Rollback |
|---|---|---|---|
| 1 | CONTRIBUTING.md (new) | Very Low | Delete file |
| 2 | CODE_OF_CONDUCT.md (new) | Very Low | Delete file |
| 3 | SKILL.md (append only) | Low | Remove added examples |
| 4 | README.md (verify link) | Very Low | Revert to original link |
| 5 | README.md (add Cursor note) | Low | Remove added section |

All PRs are low-risk, docs-only changes with straightforward rollback paths.