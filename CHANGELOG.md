# Changelog

## 2026-09-04

### Changed

- Refined the ChatGPT Custom Instructions loader to actively locate and load the current deployment file before the first substantive response in a new chat when file access is available, rather than relying on automatic retrieval.

## 2026-08-23

### Changed

- Refined artifact-production rules to distinguish superseded revision context from current artifact content, require affected content-bearing surfaces to reflect the current revision state, and preserve prior-state information when the artifact still requires it.
- Merged the superseded-content re-entry learning into the existing artifact-production rule, synchronized the ChatGPT deployment adapter and completion gate, and retired the absorbed learning entry.

## 2026-08-18

### Added

- File-level loading and canonical execution routing in `README.md`.
- Global and triggered operating rules under `rules/`.
- Domain-specific article, technical-writing, and fiction rules under `domains/`.
- Final completion validation in `quality/completion-gate.md`.
- Rule lifecycle, repository maintenance, and scheduled or event-triggered review procedures under `governance/`.
- `learnings/LEARNINGS.md` for reusable failure patterns below canonical maturity, with explicit status and disposition handling.
- A self-contained ChatGPT deployment adapter for ordinary execution without retrieving the canonical repository in every chat.
- Canonical-to-adapter synchronization requirements and coverage mapping in `governance/repository-maintenance.md`.
- `adapters/chatgpt-loader.md` as a short Custom Instructions loader for locating the current deployment copy when the full adapter exceeds the UI field limit.
- `adapters/chatgpt-daily-maintainer.md` as a reusable scheduled/manual maintenance prompt with merged-main deployment-file handoff for ChatGPT Library use, including latest-only active deployment cleanup when Library deletion is available.
- Deployment dependency tracking across runtime artifacts, explicitly separating canonical dependencies from runtime-owned behavior.
- Mozilla Public License 2.0 as the repository license, with public-facing purpose and license information in `README.md`.
- A privacy/redaction guard in the ChatGPT daily maintainer so personal or sensitive review evidence is not written into repository artifacts.
- Guidance for concise technical writing, with guidance for technical documentation on list and table choice and long English compound modifiers.
- Reuse-before-invention governance for material rule-system changes, requiring relevant existing work and precedents to be checked before repository-specific rule synthesis.
- A public-repository example policy that prefers generic or synthetic examples over unnecessary conversation-specific, user-specific, or project-specific illustrative literals in canonical rule files and public-facing repository documentation.
- Artifact-production rules for deliverable content selection, independent use, and required process or provenance information.

### Changed

- Refined terminology consistency in technical writing and synchronized the ChatGPT deployment adapter with the canonical changes.
- Refined source-grounded rule adoption records and cross-file responsibility redistribution checks.
- Redistributed general artifact-hygiene and context-independence behavior from article and completion rules into the shared artifact-production rule, with ChatGPT deployment synchronization and dependency-map updates.
