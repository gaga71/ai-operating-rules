# AI Operating Rules

A repository for maintaining reusable operating rules for AI-assisted work. The rule system separates always-applicable rules, triggered rules, domain-specific rules, completion checks, rule maintenance, reusable learnings, and platform adapters.

## File loading

Use the table below to decide which file to read. Multiple triggered rule or domain files may apply to the same task.

| File | Load when | Role |
| --- | --- | --- |
| `README.md` | entering the repository or deciding which files apply | repository map and loading entry point |
| `rules/core.md` | every canonical-rule execution | global operating contract and precedence |
| `rules/research.md` | research, search, fact-checking, literature review, source evaluation, or evidence-based investigation | research and evidence rules |
| `rules/writing-editing.md` | drafting, rewriting, editing, restructuring, or polishing prose | writing and editing rules |
| `domains/articles.md` | the final artifact is a reader-facing article | article-specific requirements |
| `domains/technical-writing.md` | the task produces or edits a technical document | technical-writing requirements |
| `domains/fiction.md` | the task involves fiction, narrative scenes, story planning, or continuity-sensitive creative writing | fiction and continuity requirements |
| `domains/reviews.md` | the task is a review, critique, audit, or quality diagnosis | review and diagnosis requirements |
| `quality/completion-gate.md` | before declaring work complete | final validation gate |
| `governance/rule-lifecycle.md` | deciding whether to add, change, refine, narrow, merge, promote, or retire a learning or canonical rule | rule-level maintenance process |
| `governance/repository-maintenance.md` | changing repository structure or responsibility boundaries, managing cross-file dependencies or duplication, synchronizing deployment adapters, or applying repository metadata/changelog discipline | repository-level maintenance rules |
| `governance/daily-review.md` | scheduled daily review or event-triggered review after a material incident | review workflow from candidate collection through validation |
| `learnings/LEARNINGS.md` | recording or reviewing reusable failure patterns that are not yet canonical, comparing a new candidate with existing learnings, or considering promotion | learning queue and entry format |
| `adapters/chatgpt.md` | ordinary ChatGPT execution when the canonical repository is not being loaded into each chat | self-contained ChatGPT deployment artifact |
| `CHANGELOG.md` | checking material rule-system history or recording a material semantic or structural change | material change history; not an operating-rule source |

## Loading paths

### Canonical execution

1. Load `rules/core.md`.
2. Load only the conditional rule files whose triggers are present.
3. Load only the domain files whose triggers are present.
4. Apply `quality/completion-gate.md` before declaring completion.

### ChatGPT deployment

Use `adapters/chatgpt.md` as the self-contained ordinary-execution artifact when repository retrieval is unavailable or unnecessary in each chat. The canonical files remain the maintenance source.

### Rule-system maintenance

- Use `governance/rule-lifecycle.md` for rule-level decisions.
- Use `governance/repository-maintenance.md` when a change crosses repository responsibilities, affects deployment synchronization, or otherwise meets that file's loading condition.
- Use `governance/daily-review.md` for scheduled daily reviews and event-triggered reviews.
- Consult `learnings/LEARNINGS.md` when a candidate learning is being recorded, compared, updated, merged, promoted, or retired.
- Record material semantic or structural changes in `CHANGELOG.md`.

## Canonical rules

The canonical rules are maintained under `rules/`, `domains/`, `quality/`, and `governance/`. Platform adapters are deployment artifacts for specific environments and do not override canonical rules.

## Precedence

Current explicit instruction > fixed or preserved project decisions > global rules > triggered conditional rules > relevant domain-specific rules > general style preferences.

## Rule maintenance

Diagnose recurring failures before adding rules. Refine, narrow, or merge an existing rule when it can represent the failure adequately. Keep reusable but not yet mature patterns in `learnings/LEARNINGS.md` until promotion is justified.
