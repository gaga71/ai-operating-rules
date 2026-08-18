# AI Operating Rules

A repository for maintaining reusable operating rules for AI-assisted work. The rule system separates always-applicable rules, triggered rules, domain-specific rules, completion checks, rule maintenance, reusable learnings, and platform adapters.

## File loading

Use the table below to decide which file to read. Multiple triggered rule, domain, or governance files may apply to the same task.

| File | Load when | Role |
| --- | --- | --- |
| `README.md` | entering the repository or deciding which files apply | repository map and loading entry point |
| `rules/core.md` | every canonical execution, including rule-system maintenance | global operating contract and precedence |
| `rules/research.md` | research, search, fact-checking, literature review, source evaluation, or evidence-based investigation | research and evidence rules |
| `rules/writing-editing.md` | drafting, rewriting, editing, restructuring, or polishing prose | writing and editing rules |
| `rules/reviewing.md` | the task is a review, critique, audit, or quality diagnosis | review and diagnosis rules |
| `domains/articles.md` | the final artifact is a reader-facing article | article-specific requirements |
| `domains/technical-writing.md` | the task produces or edits a technical document | technical-writing requirements |
| `domains/fiction.md` | the task involves fiction, narrative scenes, story planning, or continuity-sensitive creative writing | fiction and continuity requirements |
| `quality/completion-gate.md` | before declaring work complete in canonical execution, including rule-system maintenance | final validation gate |
| `governance/rule-lifecycle.md` | deciding whether to add, change, refine, narrow, merge, promote, or retire a learning or canonical rule | rule-level maintenance process and rule classification |
| `governance/repository-maintenance.md` | changing repository structure or responsibility boundaries, managing cross-file dependencies or duplication, synchronizing deployment adapters, or applying repository metadata/changelog discipline | repository-level maintenance rules |
| `governance/daily-review.md` | scheduled daily review or event-triggered review after a material incident | review orchestration workflow |
| `learnings/LEARNINGS.md` | recording or reviewing a reusable failure pattern, comparing a candidate with existing learnings, or considering update, merge, promotion, or retirement | learning queue and entry format |
| `adapters/chatgpt.md` | ordinary ChatGPT execution when the canonical repository is not being loaded into each chat | full self-contained ChatGPT deployment artifact |
| `adapters/chatgpt-loader.md` | configuring short ChatGPT Custom Instructions that locate a current deployment file instead of embedding the full adapter | Custom Instructions loader and usage notes |
| `adapters/chatgpt-daily-maintainer.md` | scheduling or manually running ChatGPT maintenance review and deployment-file handoff | reusable daily/event maintainer prompt |
| `CHANGELOG.md` | checking material rule-system history or recording a material semantic or structural change | material change history; not an operating-rule source |

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

When the ChatGPT Custom Instructions field cannot hold the full adapter, use `adapters/chatgpt-loader.md` as the short loader. The loader may point ChatGPT to the newest accessible deployment file saved in the current chat, project, or Library. Automatic file retrieval is not assumed; attach or select the current deployment file explicitly when reliable application is required and it was not retrieved automatically.

Use `adapters/chatgpt-daily-maintainer.md` for scheduled or manual rule-system review. Its deployment-file handoff produces a date- and commit-identified copy of the merged `main` version of `adapters/chatgpt.md`; it does not make an unmerged maintenance PR authoritative.

Rule-system maintenance is not performed from the ordinary-execution adapter or loader alone; use the canonical execution path above.

## Canonical source

Canonical rules are maintained under `rules/`, `domains/`, `quality/`, and `governance/`. Platform adapters and runtime prompts are deployment artifacts for specific environments and do not override canonical rules.