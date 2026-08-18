# Repository Maintenance

Use these rules when changing repository structure or responsibility boundaries, managing cross-file dependencies or duplication, synchronizing deployment adapters, or applying repository metadata and changelog discipline.

Do not use this file as a substitute for `governance/rule-lifecycle.md` when the decision concerns whether an individual learning or canonical rule should be added, changed, refined, narrowed, merged, promoted, or retired. Apply both files when a rule-level decision also affects repository-level responsibilities or dependencies.

Use `governance/daily-review.md` when maintenance is being performed as part of a scheduled daily review or event-triggered review.

## Responsibility boundaries

Keep the following responsibilities distinct:

- `rules/` — global and task-triggered operating rules.
- `domains/` — domain-specific rules.
- `quality/` — completion and validation checks.
- `governance/` — maintenance rules for the rule system and repository.
- `learnings/` — reusable failure patterns that have not yet become canonical rules.
- `adapters/` — deployment artifacts for specific environments.
- `CHANGELOG.md` — material changes to the rule system.

Do not move content between these responsibilities merely for convenience. Place each rule according to its actual scope and function.

## Canonical and deployment layers

The canonical maintenance source is the rule system under `rules/`, `domains/`, `quality/`, and `governance/`.

`adapters/chatgpt.md` is a self-contained deployment version for ordinary ChatGPT execution. It must remain usable without retrieving the canonical execution files during each chat, but it does not replace the canonical maintenance source.

When exact rule wording, rule maintenance, or repository updates are required, use the canonical files.

## Avoid duplication

Do not duplicate the same canonical rule across multiple files. Keep shared rules in the narrowest appropriate common location and keep domain files limited to domain-specific requirements.

Duplication inside a deployment adapter is allowed when needed for self-contained execution, but the canonical source of that content must remain identifiable.

## Cross-file change discipline

When a structural or cross-file change moves, rewrites, or redistributes rule content, preserve the intended trigger, scope, precedence, meaning, and verification behavior unless the change explicitly targets one of those properties.

Prefer semantic coverage over preserving historical wording. A rewrite is acceptable only if the resulting rule retains the required meaning and does not silently broaden, narrow, or weaken its application.

After structural or cross-file changes, re-check dependent files rather than reviewing only the edited file.

## Adapter synchronization

Treat canonical changes as dependencies of `adapters/chatgpt.md` when they affect ordinary ChatGPT execution.

After a relevant canonical change:

1. Determine which deployed adapter content is affected.
2. Update the adapter when necessary.
3. Verify that the adapter remains self-contained for ordinary execution.
4. Verify meaning-preserving parity for the affected requirements, including trigger, scope, precedence, substantive rule meaning, and verification behavior.

Do not leave the adapter silently stale after a canonical change that affects deployed behavior.

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
