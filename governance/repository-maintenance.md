# Repository Maintenance

Use these rules when changing repository structure or responsibility boundaries, managing cross-file dependencies or duplication, synchronizing deployment adapters, or applying repository metadata and changelog discipline.

Do not use this file as a substitute for `governance/rule-lifecycle.md` when the decision concerns whether an individual learning or canonical rule should be added, changed, refined, narrowed, merged, promoted, or retired. Apply both files when a rule-level decision also affects repository-level responsibilities or dependencies.

Use `governance/daily-review.md` when maintenance is being performed as part of a scheduled daily review or event-triggered review.

## Responsibility boundaries

Keep the following responsibilities distinct:

- `README.md` — repository map, file-level loading conditions, and routing entry point.
- `rules/` — global and task-triggered operating rules.
- `domains/` — domain-specific rules.
- `quality/` — completion and validation checks.
- `governance/` — maintenance rules for the rule system and repository.
- `learnings/` — reusable failure patterns that have not yet become canonical rules, plus limited retained retired entries.
- `adapters/` — deployment artifacts for specific environments.
- `CHANGELOG.md` — material changes to the rule system.

Do not move content between these responsibilities merely for convenience. Place each rule according to its actual scope and function.

When a file is added, removed, moved, or has a materially changed loading condition or role, update the corresponding `README.md` loading and routing information.

## Canonical and deployment layers

The canonical maintenance source is the rule system under `rules/`, `domains/`, `quality/`, and `governance/`.

`adapters/chatgpt.md` is a self-contained deployment version for ordinary ChatGPT execution. It must remain usable without retrieving the canonical execution files during each chat, but it does not replace the canonical maintenance source.

Other files under `adapters/` may provide runtime loaders or maintenance prompts. When they reproduce or depend on canonical operating or maintenance behavior, keep those canonical dependencies identifiable in the deployment coverage map below.

When exact rule wording, rule maintenance, or repository updates are required, use the canonical files.

## Avoid duplication

Do not duplicate the same canonical rule across multiple canonical files. Keep shared rules in the narrowest appropriate common location and keep domain files limited to domain-specific requirements.

Duplication inside a deployment artifact is allowed when needed for self-contained or reliable runtime execution, but the canonical source of duplicated content must remain identifiable through the deployment coverage map below.

## Cross-file change discipline

When a structural or cross-file change moves, rewrites, or redistributes rule content, preserve the intended trigger, scope, precedence, meaning, and verification behavior unless the change explicitly targets one of those properties.

Prefer semantic coverage over preserving historical wording. A rewrite is acceptable only if the resulting rule retains the required meaning and does not silently broaden, narrow, or weaken its application.

After structural or cross-file changes, re-check dependent files rather than reviewing only the edited file.

## Deployment coverage map

Use this map when checking synchronization between deployment artifacts and the canonical rule system.

| Deployment artifact or section | Canonical source |
| --- | --- |
| `adapters/chatgpt.md` — Precedence; Global operating rules | `rules/core.md` |
| `adapters/chatgpt.md` — Research rules | `rules/research.md` |
| `adapters/chatgpt.md` — Writing and editing rules | `rules/writing-editing.md` |
| `adapters/chatgpt.md` — Review rules | `rules/reviewing.md` |
| `adapters/chatgpt.md` — Article rules | `domains/articles.md` |
| `adapters/chatgpt.md` — Technical-writing rules | `domains/technical-writing.md` |
| `adapters/chatgpt.md` — Fiction rules | `domains/fiction.md` |
| `adapters/chatgpt.md` — Completion gate | `quality/completion-gate.md` |
| `adapters/chatgpt.md` — Rule-system maintenance routing | `README.md` and applicable files under `governance/` |
| `adapters/chatgpt-loader.md` — deployment lookup, precedence boundary, and canonical maintenance handoff | `README.md`, `rules/core.md`, and this file |
| `adapters/chatgpt-daily-maintainer.md` — maintenance startup, review orchestration, candidate routing, repository-write constraints, completion, and deployment handoff | `README.md`, `rules/core.md`, `governance/daily-review.md`, `governance/rule-lifecycle.md`, this file, `learnings/LEARNINGS.md`, and `quality/completion-gate.md` |

## Deployment synchronization

Treat canonical changes as dependencies of every deployment artifact that reproduces or depends on the changed canonical behavior.

After a relevant canonical change:

1. Use the deployment coverage map above to identify every affected deployment artifact or section.
2. Update each affected deployment artifact when necessary.
3. Verify that the coverage map still identifies the correct canonical source.
4. Verify that each affected artifact still performs its intended runtime role, including self-contained execution or loader behavior where applicable.
5. Verify meaning-preserving parity for duplicated canonical requirements, including trigger, scope, precedence, substantive rule meaning, and verification behavior.

Do not leave a deployment artifact silently stale after a canonical change that affects behavior it reproduces or depends on.

## Metadata separation

Keep design history, chat history, research history, temporary migration notes, and explanations of why a repository structure was chosen out of canonical rule files unless that information is itself required for operation or maintenance.

Repository documents should describe the current rule system rather than depend on the conversation or process that produced it.

## Changelog

Record material semantic or structural changes in `CHANGELOG.md`, including:

- new canonical rules;
- changes to rule meaning, scope, trigger, precedence, or verification;
- movement of responsibility between files;
- promotion, merge, or retirement of rules;
- deployment-adapter changes that materially affect behavior;
- material changes to governance or repository structure.

Do not use the changelog as a TODO list, chat log, or detailed record of every wording edit.

Before declaring repository-maintenance work complete, apply `quality/completion-gate.md` as required by the canonical execution path.
