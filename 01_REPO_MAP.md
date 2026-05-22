# 01_REPO_MAP.md — directional-prompting

## What the Repo Does

A two-layer prompting skill/methodology for AI coding agents (Claude Code, OpenAI Codex CLI, Cursor, etc.). Teaches the "directional prompting" pattern: open with an **outcome block** (goal, success criteria, stopping condition) then write every sentence with **positive directional verbs** so wrong behavior has no room to exist.

It is a plugin distribution system, not a code library. No runtime, no tests, no build.

## Tech Stack

- **Format**: Markdown documentation + YAML metadata + JSON plugin manifest
- **No code**: No JavaScript, Python, or any language runtime required
- **Agent compatibility**: Claude Code plugin format, OpenAI Codex Skills format, Cursor rules, Continue rules, Gemini Antigravity

## Main Directories

```
directional-prompting/
├── .claude-plugin/
│   └── marketplace.json          # Plugin registry metadata (JSON)
├── plugins/
│   └── directional-prompting/
│       └── skills/
│           └── directional-prompting/
│               ├── SKILL.md       # Core skill definition (154 lines)
│               ├── agents/
│               │   └── openai.yaml   # Codex UI metadata (YAML, 4 lines)
│               └── assets/
│                   └── hero.jpeg  # README image
├── README.md                      # Root-level marketing/usage docs (167 lines)
└── LICENSE                        # MIT license
```

## Main Runtime / Execution

None. This is a static documentation/methodology repo.

- No `package.json`, no `setup.py`, no `Makefile`
- No CI workflows (no `.github/workflows/`)
- No tests

## Test Framework

None.

## Build / Lint / Docs Commands

None. To "install" the skill, users manually symlink the skill directory into their agent's skills folder per the README instructions.

## Key Files

| File | Purpose | Lines |
|---|---|---|
| `SKILL.md` | The skill definition — methodology, rules, examples | 154 |
| `README.md` | Marketing + install instructions + layout overview | 167 |
| `marketplace.json` | Plugin registry entry | 21 |
| `agents/openai.yaml` | Codex-specific display metadata (ignored by other agents) | 4 |

## Examples (from SKILL.md)

The core rewrite example:

**Before** (no outcome, 7 negatives):
```
You are a code reviewer. Don't be too harsh. Don't nitpick formatting.
Avoid making assumptions. Never approve code with obvious bugs.
```

**After** (outcome + directional):
```
Goal: Review the PR diff and decide whether to approve, request changes, or block.

Success means:
  - Verdict is one of: APPROVE, REQUEST_CHANGES, BLOCK
  - Each comment names the file, line, and replacement code
  - Comments cover correctness, security, clarity

Stop when: A verdict is issued and every comment is actionable.

Focus on bugs you can reproduce. Ask before interpreting intent.
Block merges on reproducible bugs. Write in plain text.
```

## Risk-Sensitive Areas

- **README is the public face** — any changes to install instructions could confuse users
- **SKILL.md is the core logic** — the methodology must remain accurate and self-consistent
- **marketplace.json** must remain valid JSON for plugin registry compatibility
- The repo has 78 stars and 7 forks — active community use

## Areas Likely Safe for Small PRs

- **Minor typos or grammar fixes** in README or SKILL.md
- **Adding agent compatibility entries** (e.g., adding another row to the compatibility table in README) if the pattern is correct
- **Clarifying install instructions** if they are genuinely unclear
- **Link fixes** — broken links in markdown

## What to Avoid

- Changing the core methodology (outcome + directional layers) without deep consideration
- Modifying the skill trigger logic or application checklist without understanding agent behavior
- Touching `hero.jpeg` (binary asset)
- Changing LICENSE — it's MIT and should stay that way

## Contributing

No formal CONTRIBUTING.md or CODE_OF_CONDUCT.md found. The README itself serves as the primary documentation.