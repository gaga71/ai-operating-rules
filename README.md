# AI Operating Rules

A repository for maintaining reusable operating rules for AI-assisted work. The rule system separates always-applicable rules, triggered rules, domain-specific rules, completion checks, rule maintenance, reusable learnings, and platform adapters.

## Structure

- `rules/core.md` — minimal operating contract applied to all work.
- `rules/research.md` — rules for research, search, fact-checking, source evaluation, and evidence-based investigation.
- `rules/writing-editing.md` — rules for drafting, rewriting, editing, restructuring, and polishing prose.
- `domains/` — rules that apply only to the relevant artifact or work domain.
- `quality/completion-gate.md` — checks required before declaring work complete.
- `governance/rule-lifecycle.md` — process for refining, promoting, merging, and retiring rules.
- `learnings/LEARNINGS.md` — reusable failure patterns that have not yet become canonical rules.
- `adapters/chatgpt.md` — compact entry and routing instructions for ChatGPT.
- `CHANGELOG.md` — material changes to the rule system.

## Loading model

1. Apply `rules/core.md` to all work.
2. Load a conditional rule file only when its trigger is present.
3. Load a domain file only when the task belongs to that domain.
4. Apply `quality/completion-gate.md` before declaring completion.
5. Use `governance/rule-lifecycle.md` when maintaining the rule system.

Multiple conditional and domain files may apply to the same task.

## Canonical rules

The canonical rules are maintained under `rules/`, `domains/`, `quality/`, and `governance/`. Platform adapters are entry points for specific environments and do not override canonical rules.

## Precedence

Current explicit instruction > fixed or preserved project decisions > global rules > triggered conditional rules > relevant domain-specific rules > general style preferences.

## Rule maintenance

Diagnose recurring failures before adding rules. Refine, narrow, or merge an existing rule when it can represent the failure adequately. Keep reusable but not yet mature patterns in `learnings/LEARNINGS.md` until promotion is justified.
