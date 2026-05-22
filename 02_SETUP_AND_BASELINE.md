# 02_SETUP_AND_BASELINE.md — directional-prompting

## Repository Type

**Documentation/methodology repository** — no code, no tests, no CI.

This repo is a plugin distribution system for the "directional prompting" methodology. It ships SKILL.md and README.md as the primary deliverables. No runtime, no build system, no test framework.

## Baseline Inventory

| Item | Status | Notes |
|---|---|---|
| package.json | None | Not a JS project |
| pyproject.toml | None | Not a Python project |
| Test framework | None | No tests |
| CI/CD | None | No .github/workflows/ |
| Build system | None | N/A |
| Runtime | None | Static documentation |

## Primary Product Files

| File | Purpose | Valid? |
|---|---|---|
| `SKILL.md` | Core skill definition — methodology, rules, examples | ✅ Well-formed Markdown, 154 lines |
| `README.md` | Marketing + install instructions + layout overview | ✅ Well-formed Markdown, 167 lines |
| `marketplace.json` | Plugin registry entry | ✅ Valid JSON, 21 lines |
| `agents/openai.yaml` | Codex UI metadata (4 lines) | ✅ Valid YAML |

## Repository Structure

```
directional-prompting/
├── .claude-plugin/
│   └── marketplace.json          # Plugin registry metadata
├── plugins/
│   └── directional-prompting/
│       └── skills/
│           └── directional-prompting/
│               ├── SKILL.md       # Core skill (154 lines)
│               ├── agents/
│               │   └── openai.yaml # Codex metadata (4 lines)
│               └── assets/
│                   └── hero.jpeg   # README image
├── README.md                      # Root docs (167 lines)
├── LICENSE                        # MIT
└── [campaign docs]
    ├── 00_STATE.md
    ├── 01_REPO_MAP.md
    └── [this file]
```

## Key Observations

1. **No runtime dependencies** — pure documentation/methodology repo
2. **Agent compatibility is the "product"** — SKILL.md and openai.yaml must be valid for Claude Code and Codex respectively
3. **Single contributor** (Bootoshi) — 78 stars, 7 forks on upstream
4. **No CONTRIBUTING.md or CODE_OF_CONDUCT.md** — README serves as primary documentation
5. **No formal issue/PR activity** — zero open issues, zero open PRs, no recently merged PRs visible

## Install Verification

The skill is installed by symlinking `plugins/directional-prompting/skills/directional-prompting/` into the agent's skills directory. The README documents this for Claude Code and Codex CLI.