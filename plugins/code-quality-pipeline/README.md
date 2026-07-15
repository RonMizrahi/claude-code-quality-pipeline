# Code Quality Pipeline

By **[Ron Mizrahi](https://github.com/RonMizrahi)**.

The quality gates that stand between "code written" and "code merged." This plugin ships a single
skill, `code-quality-pipeline`, that Claude loads automatically the moment implementation is
complete and you're heading toward an MR/PR.

## What it does

Two complementary gates:

- **Gate A — per-file pipeline** — after a milestone's unit + integration tests pass and before
  e2e: **Code Review → Code Simplification → Security Review → Final Review**, each step fanning out
  one subagent per changed file, feedback applied between steps.
- **Gate B — holistic pre-merge review** — right before opening the MR/PR: one review of the
  **entire diff against main** to catch cross-file interactions Gate A can't see.

## Install

```
/plugin marketplace add RonMizrahi/claude-plugins
/plugin install code-quality-pipeline@ron-mizrahi
```

## Trigger it

The skill auto-loads when implementation is done, or ask for it directly:

> run the pipeline · code quality check · review before e2e · pre-merge review

## Dependencies

The pipeline **orchestrates** review tools rather than bundling them. For full coverage, also have
available: `feature-dev:code-reviewer` (Code Review steps), `code-simplifier` (Simplification),
the built-in `security-review` (Security), and `code-review:code-review` (Gate B). Any missing
tool means that step is skipped and reported as skipped — never silently passed.

## License

MIT © Ron Mizrahi
