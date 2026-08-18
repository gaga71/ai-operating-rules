# AI Operating Rules

A version-controlled framework for maintaining, applying, and evolving reusable operating rules for AI-assisted work across research, writing, review, and other workflows. It separates canonical rules from platform-specific deployment artifacts and defines explicit paths for validation, learning, and rule-system maintenance.

## File loading

Use the table below to decide which file to read. Multiple triggered rule, domain, or governance files may apply to the same task.

| File | Load when | Role |
| --- | --- | --- |
| `README.md` | entering the repository or deciding which files apply | repository map and loading entry point |
| `rules/core.md` | every canonical execution, including rule-system maintenance | global operating contract and precedence |
| `rules/artifact-production.md` | creating, editing, transforming, or delivering a distinct deliverable intended to be retained, reused, handed off, published, or used independently of the surrounding conversation | artifact content selection, context independence, process/provenance placement, and artifact-level verification |
| `rules/research.md` | research, search, fact-checking, literature review, source evaluation, or evidence-based investigation | research and evidence rules |
| `rules/writing-editing.md` | drafting, rewriting, editing, restructuring, or polishing prose | writing and editing rules |
| `rules/reviewing.md` | the task is a review, critique, audit, or quality diagnosis | review and diagnosis rules |
| `domains/articles.md` | the final artifact is a reader-facing article | article-specific requirements |
| `domains/technical-writing.md` | the task produces or edits a technical document | technical-writing requirements |
| `domains/fiction.md` | the task involves fiction, narrative scenes, story planning, or continuity-sensitive creative writing | fiction and continuity requirements |
| `quality/completion-gate.md` | before declaring work complete in canonical execution, including rule-system maintenance | final validation gate |
| `governance/rule-lifecycle.md` | deciding whether to add, change, refine, narrow, merge, promote, or retire a learning or canonical rule | rule-level maintenance process and rule classification |
| `governance/repository-maintenance.md` | changing repository structure or responsibility boundaries, managing cross-file dependencies or duplication, synchronizing deployment artifacts, or applying repository metadata, licensing, or changelog discipline | repository-level maintenance rules |
| `governance/daily-review.md` | scheduled daily review or event-triggered review after a material incident | review orchestration workflow |
| `learnings/LEARNINGS.md` | recording or reviewing a reusable failure pattern, comparing a candidate with existing learnings, or considering update, merge, promotion, or retirement | learning queue and entry format |
| `adapters/chatgpt.md` | ordinary ChatGPT execution when the canonical repository is not being loaded into each chat | full self-contained ChatGPT deployment artifact |
| `adapters/chatgpt-loader.md` | configuring short ChatGPT Custom Instructions that locate a current deployment copy instead of embedding the full adapter | Custom Instructions loader and usage notes |
| `adapters/chatgpt-daily-maintainer.md` | scheduling or manually running ChatGPT maintenance review and deployment-file handoff | reusable daily/event maintainer prompt |
| `CHANGELOG.md` | checking material rule-system history or recording a material semantic or structural change | material change history; not an operating-rule source |
| `LICENSE` | checking reuse, modification, or redistribution terms | Mozilla Public License 2.0 governing this repository |

## Canonical execution path

Use one canonical execution path for both ordinary work and rule-system maintenance:

1. Load `rules/core.md`.
2. Load only the conditional rule files whose triggers are present.
3. Load only the domain files whose triggers are present.
4. For rule-system maintenance, load the applicable governance files and `learnings/LEARNINGS.md` when required by their loading conditions.
5. Apply `quality/completion-gate.md` before declaring the work complete.

### Rule-system maintenance routing

Within the canonical execution path:

- Use `governance/rule-lifecycle.md` for rule-level decisions and rule classification.
- Use `governance/repository-maintenance.md` when a change crosses repository responsibilities, affects deployment synchronization, or otherwise meets that file's loading condition.
- Use `governance/daily-review.md` to orchestrate scheduled daily reviews and event-triggered reviews.
- Consult `learnings/LEARNINGS.md` when a candidate learning is being recorded, compared, updated, merged, promoted, or retired.
- Record material semantic or structural changes in `CHANGELOG.md`.

## ChatGPT deployment

`adapters/chatgpt.md` is the maintained full ordinary-execution deployment artifact.

Use `adapters/chatgpt-loader.md` when a short Custom Instructions loader is needed instead of embedding the full adapter. See that file for deployment-file lookup and fallback behavior.

Use `adapters/chatgpt-daily-maintainer.md` for scheduled or manual rule-system review and merged-main deployment-file handoff. See that file for runtime execution and Library-handling details.

Rule-system maintenance is not performed from the ordinary-execution adapter or loader alone; use the canonical execution path above.

## Canonical source

Canonical rules are maintained under `rules/`, `domains/`, `quality/`, and `governance/`. Platform adapters and runtime prompts are deployment artifacts for specific environments and do not override canonical rules.

## License

This repository is licensed under the Mozilla Public License 2.0. See [LICENSE](LICENSE).
