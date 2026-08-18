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

- Clarified file-level loading conditions and separated canonical execution, ChatGPT deployment, and rule-system maintenance paths in `README.md`.
- Narrowed the boundary between rule-level lifecycle decisions and repository-level maintenance responsibilities.
- Required adapter synchronization when a canonical change affects ordinary ChatGPT execution.
- Added comparison against existing learnings during review and rule-lifecycle decisions to prevent duplicate learning entries.
- Defined operational meanings and transition conditions for existing learning statuses.
- Refocused `adapters/chatgpt.md` on ordinary execution and routed rule-system maintenance to canonical governance files.
- Reduced `domains/articles.md` to article-specific requirements while leaving general prose structure to `rules/writing-editing.md`.

### Migration

The previous ten-rule set was reorganized by responsibility into global operation, triggered rules, domain-specific rules, completion validation, rule-system governance, learnings, and a ChatGPT deployment adapter.
