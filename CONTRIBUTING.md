# Contributing to Directional Prompting

Thank you for your interest in contributing. Directional Prompting is a skill for writing better prompts — contributions should follow the same principles the skill teaches: outcome-first, directional prose, and positive framing.

## How to Contribute

### Reporting Issues

Open an issue with:
- **Goal:** What you are trying to do
- **Problem:** What goes wrong
- **Example:** A before/after that demonstrates the gap

Skip "would be nice" proposals without a concrete use case. Feature requests need a real-world scenario where directional prompting currently fails.

### Submitting Changes

1. **Fork and branch** — use `pr/<campaign>/<short-description>` naming
2. **Write the change outcome-first** — open with `Goal:`, `Success means:`, `Stop when:`
3. **Use directional prose** — every sentence leads with a positive verb
4. **No negation in the body** — avoid `don't`, `do not`, `never`, `avoid`
   - Exception: hard safety boundaries, disambiguating near-identical paths, acceptable spaces too large to enumerate, specific banned items where the positive form is genuinely ambiguous
5. **Keep absolute-rule signals loud where they matter** — `ALWAYS` / `NEVER` / `MUST` stay as a signal, not decorative prose
6. **Test the skill** — invoke it in Claude Code or Codex CLI before submitting

### PR Checklist

- [ ] Branch name follows `pr/<campaign>/<short-description>`
- [ ] Opens with outcome block (`Goal:`, `Success means:`, `Stop when:`)
- [ ] Body uses positive verbs on every sentence
- [ ] No forbidden negation patterns
- [ ] Tested in at least one agent (Claude Code or Codex CLI)

## Development Setup

```bash
# Clone once
git clone https://github.com/kingbootoshi/directional-prompting.git ~/.directional-prompting

# Claude Code
mkdir -p ~/.claude/skills
ln -sfn ~/.directional-prompting/plugins/directional-prompting/skills/directional-prompting ~/.claude/skills/directional-prompting

# Codex CLI
mkdir -p ~/.codex/skills
ln -sfn ~/.directional-prompting/plugins/directional-prompting/skills/directional-prompting ~/.codex/skills/directional-prompting
```

## Project Structure

```
plugins/
  directional-prompting/
    skills/
      directional-prompting/
        SKILL.md          # Core skill definition
        assets/           # Images and diagrams
```

## Principles

1. **Outcome first** — name the destination before naming the path
2. **Direction in every sentence** — positive verbs, not prohibitions
3. **Test with real agents** — Claude Code or Codex CLI, not just in theory

Questions? Open an issue with the `question` label.
