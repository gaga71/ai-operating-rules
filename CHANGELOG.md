# Changelog

## 2026-08-18

### Added

- Initial canonical operating-rule structure.
- Global operating contract in `rules/core.md`.
- Triggered research, writing/editing, and reviewing rules under `rules/`.
- Article, technical-writing, and fiction domain rules under `domains/`.
- Completion gate for final validation.
- Rule lifecycle governance in `governance/rule-lifecycle.md`.
- Repository structure and synchronization governance in `governance/repository-maintenance.md`.
- Scheduled daily and event-triggered review workflow in `governance/daily-review.md`.
- Learnings queue for reusable failure patterns that are not yet canonical.
- Self-contained ChatGPT deployment adapter for ordinary execution without repository retrieval in every chat.

### Changed

- Unified ordinary canonical execution and rule-system maintenance under the same `rules/core.md` entry and `quality/completion-gate.md` final gate.
- Kept `README.md` focused on file-level loading and routing rather than duplicating canonical precedence or maintenance rules.
- Moved review, critique, audit, and quality-diagnosis rules from `domains/reviews.md` to the triggered rule file `rules/reviewing.md`.
- Moved rule classification and the Trigger / Failure mode / Rule / Verification authoring schema from `rules/core.md` to `governance/rule-lifecycle.md`.
- Narrowed the boundary between rule-level lifecycle decisions and repository-level maintenance responsibilities.
- Made `governance/rule-lifecycle.md` the source of truth for maintenance dispositions and added an explicit **Add** path for persistent authoritative requirements or deliberately adopted operating policies without allowing isolated failures to bypass learning maturity.
- Clarified that `ready-for-promotion` is eligibility for a promotion decision rather than approval.
- Reduced `governance/daily-review.md` to orchestration and moved anti-recency and anti-salience controls into review-scope selection before candidate triage.
- Added comparison against existing learnings during review and rule-lifecycle decisions to prevent duplicate learning entries.
- Aligned learning status semantics with the entry schema by supporting multiple observations, making candidate rules optional until sufficiently mature, and aligning the entry disposition field with `governance/rule-lifecycle.md`.
- Defined review and retirement conditions for stale or no-longer-useful learning candidates without adding a time-based expiry rule.
- Defined minimal retention and removal conditions for retired learning entries so that `learnings/LEARNINGS.md` does not become a permanent failure archive.
- Moved the ChatGPT adapter coverage map into `governance/repository-maintenance.md`, where deployment synchronization is maintained.
- Added an explicit `quality/completion-gate.md` exit to repository-maintenance work.
- Removed rule-authoring metadata from `adapters/chatgpt.md` while preserving its self-contained ordinary-execution rules.
- Restored ChatGPT adapter parity with canonical research and review rules for negative-finding search scope and mandatory root-cause recommendations.
- Clarified that `quality/completion-gate.md` applies to both ordinary tasks and rule-system maintenance performed through the canonical execution path.
- Reduced `domains/articles.md` to article-specific requirements while leaving general prose structure to `rules/writing-editing.md`.

### Migration

The previous ten-rule set was reorganized by responsibility into global operation, triggered rules, domain-specific rules, completion validation, rule-system governance, learnings, and a ChatGPT deployment adapter.
