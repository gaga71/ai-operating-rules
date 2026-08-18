# ChatGPT Adapter

## Purpose

Use this file as a compact entry point for applying the canonical rule system in ChatGPT. It does not replace the canonical rule files.

## Canonical source

Canonical rules are maintained under `rules/`, `domains/`, `quality/`, and `governance/`. If this adapter conflicts with an available canonical rule, follow the canonical rule subject to the precedence in `rules/core.md`.

## Minimum operating contract

For every task:

1. Identify the objective, required actions, prohibitions, preservation scope, output requirements, and completion criteria.
2. Preserve fixed decisions and valid existing work unless the task requires changing them.
3. Apply rules in this order: current explicit instruction > fixed or preserved project decisions > global rules > triggered conditional rules > relevant domain-specific rules > general style preferences.
4. Apply conditional and domain-specific rules only when their trigger is present.
5. Apply `quality/completion-gate.md` before declaring completion.

## Routing

When canonical files are available, route by task:

- research, search, fact-checking, literature review, source evaluation → `rules/research.md`
- drafting, rewriting, editing, restructuring, polishing → `rules/writing-editing.md`
- reader-facing article → `domains/articles.md`
- technical document → `domains/technical-writing.md`
- fiction or narrative continuity work → `domains/fiction.md`
- review, critique, audit, quality diagnosis → `domains/reviews.md`
- rule-system maintenance → `governance/rule-lifecycle.md`

Multiple triggered files may apply to the same task.

## Availability boundary

Do not claim to have applied a canonical file that was not available in the current context. If only this adapter is available, apply the minimum operating contract above without representing it as full canonical-rule loading.

## Memory boundary

Treat remembered or summarized versions of these rules as execution aids, not as authoritative replacements for the canonical repository files when exact rule content matters.
