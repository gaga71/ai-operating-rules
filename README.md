# AI Operating Rules

A repository for maintaining reusable operating rules for AI-assisted work. The repository separates always-applicable rules, triggered rules, domain rules, completion checks, rule lifecycle management, reusable learnings, and platform adapters.

## Structure

- `rules/core.md` — minimal operating contract applied to all work.
- `rules/research.md` — rules loaded for research, search, fact-checking, and evidence evaluation.
- `rules/writing-editing.md` — rules loaded for drafting, editing, and restructuring prose.
- `domains/` — rules loaded only for the relevant output domain.
- `quality/completion-gate.md` — checks required before declaring work complete.
- `governance/rule-lifecycle.md` — how failures become learnings, rules are refined, and stale rules are retired.
- `learnings/LEARNINGS.md` — reusable failure patterns that have not yet become canonical rules.
- `adapters/chatgpt.md` — compact entry and routing instructions for ChatGPT.
- `CHANGELOG.md` — semantic changes to the rule system.

## Loading model

1. Load `rules/core.md` for all work.
2. Load a conditional rule file only when its trigger is present.
3. Load a domain file only when the final artifact belongs to that domain.
4. Apply `quality/completion-gate.md` before declaring completion.
5. Use `governance/rule-lifecycle.md` when maintaining the rule system.

## Source of truth

The canonical rules are the files under `rules/`, `domains/`, `quality/`, and `governance/`. Platform adapters are derived entry points and must not silently override canonical rules.

## Precedence

Current explicit instruction > fixed or preserved project decisions > global rules > triggered conditional rules > relevant domain-specific rules > general style preferences.

## Rule maintenance

Recurring failures are diagnosed before a new rule is added. Existing rules should be refined, narrowed, or merged where they can adequately represent the failure. Reusable but not yet mature patterns belong in `learnings/LEARNINGS.md` before promotion to canonical rules.

## Design basis

The repository structure follows patterns used by existing AI operating-rule and memory projects: a small canonical operating contract, task-triggered loading, completion validation, a learning-to-rule promotion path, and platform-specific adapters. Reference implementations include [AI-shared-memory](https://github.com/JSvandijk/AI-shared-memory), [Mira](https://github.com/byteseek/Mira), [AI Operating Process Starter Kit](https://github.com/Glenskii/ai-operating-process-starter-kit), and [Agent Librarian](https://github.com/ElvinMorales/agent-librarian).
