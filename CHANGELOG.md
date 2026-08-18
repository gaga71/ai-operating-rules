# Changelog

## 2026-08-18

### Added

- Initial canonical operating-rule structure.
- Global operating contract in `rules/core.md`.
- Triggered research and writing/editing rules.
- Article, technical-writing, fiction, and review domain rules.
- Completion gate for final validation.
- Rule lifecycle governance in `governance/rule-lifecycle.md`.
- Repository structure and synchronization governance in `governance/repository-maintenance.md`.
- Scheduled daily and event-triggered review workflow in `governance/daily-review.md`.
- Learnings queue for reusable failure patterns that are not yet canonical.
- Self-contained ChatGPT deployment adapter for ordinary execution without repository retrieval in every chat.

### Changed

- Unified ordinary canonical execution and rule-system maintenance under the same `rules/core.md` entry and `quality/completion-gate.md` final gate.
- Clarified file-level loading conditions and maintenance routing in `README.md`.
- Narrowed the boundary between rule-level lifecycle decisions and repository-level maintenance responsibilities.
- Made `governance/rule-lifecycle.md` the source of truth for maintenance dispositions and clarified that `ready-for-promotion` is eligibility for a promotion decision rather than approval.
- Reduced `governance/daily-review.md` to orchestration, delegating rule decisions, repository synchronization, and final completion validation to their canonical responsibility files.
- Added comparison against existing learnings during review and rule-lifecycle decisions to prevent duplicate learning entries.
- Aligned learning status semantics with the entry schema by supporting multiple observations and making candidate rules optional until sufficiently mature.
- Added a canonical coverage map to `adapters/chatgpt.md` and tied adapter synchronization checks to that map.
- Refocused `adapters/chatgpt.md` on ordinary execution and routed rule-system maintenance to the canonical execution path.
- Reduced `domains/articles.md` to article-specific requirements while leaving general prose structure to `rules/writing-editing.md`.

### Migration

The previous ten-rule set was reorganized by responsibility into global operation, triggered rules, domain-specific rules, completion validation, rule-system governance, learnings, and a ChatGPT deployment adapter.
