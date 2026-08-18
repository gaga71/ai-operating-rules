# ChatGPT Adapter

## Purpose

This file is a compact entry point for using the canonical rule system in ChatGPT. It is not a replacement for the canonical rule files.

## Canonical source

Canonical rules are maintained under:

- `rules/`
- `domains/`
- `quality/`
- `governance/`

If this adapter conflicts with a canonical rule that is available, follow the canonical rule subject to the precedence defined in `rules/core.md`.

## Minimum operating contract

For every task:

1. Identify the objective, required actions, prohibitions, preservation scope, output requirements, and completion criteria.
2. Preserve fixed decisions and valid existing work unless the task requires changing them.
3. Apply rules in this order: current explicit instruction > fixed/preserved project decisions > global rules > triggered conditional rules > relevant domain-specific rules > general style preferences.
4. Do not load or apply conditional or domain-specific rules without their trigger.
5. Apply `quality/completion-gate.md` before declaring completion.

## Routing

When the relevant canonical files are available, route by task:

- research, search, fact-checking, literature review, evidence evaluation → `rules/research.md`
- drafting, rewriting, editing, restructuring, polishing → `rules/writing-editing.md`
- reader-facing article → `domains/articles.md`
- technical document → `domains/technical-writing.md`
- fiction or narrative continuity work → `domains/fiction.md`
- review, critique, audit, quality diagnosis → `domains/reviews.md`
- rule-system maintenance → `governance/rule-lifecycle.md`

Multiple triggered files may apply to the same task.

## Availability boundary

Do not claim to have applied a canonical file that was not actually available in the current context. If only this adapter is available, use the minimum operating contract above and distinguish that state from full canonical-rule loading.

## Memory boundary

Treat remembered or summarized versions of these rules as execution aids rather than as authoritative replacements for the canonical repository files when exact rule content matters.
