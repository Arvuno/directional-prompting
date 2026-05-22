# 05_PR_CANDIDATES.md — directional-prompting

## Overview

This is a documentation/methodology repo with no code, no tests, and no CI. PR candidates focus on documentation quality, content consistency, and accessibility improvements. All candidates are low-risk, docs-only changes.

---

## Candidate 1: Add CONTRIBUTING.md

**Risk:** Low | **Effort:** Low | **Priority:** Medium

**Rationale:** The repo has 78 stars and 7 forks but no CONTRIBUTING.md. Adding one formalizes how the community can contribute, which may increase participation and reduce low-signal issues.

**Proposed content:**
- Link to the directional prompting methodology (SKILL.md)
- Note that this is a documentation repo, not a code project
- Explain that contributions to the skill itself should follow the outcome + directional pattern
- Point to GitHub Issues for bug reports

---

## Candidate 2: Add Code of Conduct

**Risk:** Very Low | **Effort:** Low | **Priority:** Low

**Rationale:** Standard community health file. Many OSS watchers expect CODE_OF_CONDUCT.md. A simple one (like Contributor Covenant) takes minutes to add and signals maintainer professionalism.

**Proposed:** Add `CODE_OF_CONDUCT.md` using the Contributor Covenant 2.1 template.

---

## Candidate 3: Add More Examples to SKILL.md

**Risk:** Low | **Effort:** Medium | **Priority:** Medium

**Rationale:** The SKILL.md has one before/after example (code reviewer). Adding 1-2 more concrete examples in different domains (e.g., system prompt for a CLI agent, skill description for a tool) would make the methodology more accessible to newcomers.

**Proposed examples:**
1. A system prompt rewrite for a file-editing agent
2. A skill description rewrite for a "test writing" skill

---

## Candidate 4: Verify External Links

**Risk:** Very Low | **Effort:** Medium | **Priority:** Low

**Rationale:** The README.md references `https://developers.openai.com/codex/skills`. This was not programmatically verified. A PR could verify the link is still valid and update if the URL has changed.

---

## Candidate 5: Clarify Install Instructions for Cursor

**Risk:** Low | **Effort:** Low | **Priority:** Low

**Rationale:** The compatibility table in README.md mentions Cursor rules at `.cursor/skills/directional-prompting/` but the install section only covers Claude Code and Codex CLI. Adding a brief Cursor install note (or a general note that the skill works wherever `SKILL.md` is read) would improve clarity.

---

## Candidate 6: Add a Badges Section to README

**Risk:** Very Low | **Effort:** Low | **Priority:** Low

**Rationale:** Many repos add shields for: license (MIT), GitHub stars, upstream compatibility. Adding a simple badges section at the top of README.md would improve visual appeal and quick-info availability.

**Proposed badges:**
- License (MIT)
- GitHub stars (78)
- Compatibility (Claude Code, Codex CLI)

---

## Candidate 7: Add Testing Notes for Skills

**Risk:** Low | **Effort:** Low | **Priority:** Low

**Rationale:** Since this is a skill repo, users may wonder "how do I test my prompt changes?" A short note explaining that the skill is validated by running it against real agent sessions (no automated test framework) would set correct expectations.

---

## Prioritization Summary

| # | Candidate | Risk | Effort | Priority |
|---|---|---|---|---|
| 1 | Add CONTRIBUTING.md | Low | Low | Medium |
| 2 | Add Code of Conduct | Very Low | Low | Low |
| 3 | More SKILL.md examples | Low | Medium | Medium |
| 4 | Verify external links | Very Low | Medium | Low |
| 5 | Clarify Cursor install | Low | Low | Low |
| 6 | Add README badges | Very Low | Low | Low |
| 7 | Add testing notes | Low | Low | Low |

## Recommendation

Focus on Candidates 1, 2, and 3 as the highest-value/low-risk set. These improve community contribution pathways and make the methodology more accessible.