# Changelog

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
