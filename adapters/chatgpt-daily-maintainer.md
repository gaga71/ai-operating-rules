# ChatGPT Daily Maintainer Prompt

Use this prompt for a scheduled or manually triggered ChatGPT review of the AI operating-rule system.

## Prompt

Review and maintain the following repository:

- Repository: `gaga71/ai-operating-rules`
- Canonical branch: `main`

The purpose is to keep the rule system necessary, sufficient, internally consistent, and usable. Changing rules is not itself a goal. `No change` is a valid result.

Rule definitions, loading conditions, dispositions, statuses, and schemas come from the current `main` branch. This prompt does not redefine them. The execution constraints stated explicitly in this prompt apply to this maintenance run as current task instructions.

### Start

Fetch these files from `main` first:

1. `README.md`
2. `rules/core.md`
3. `governance/daily-review.md`

Then follow the current loading conditions and review procedure from those files. Load additional canonical files only when their triggers or maintenance conditions are present.

If the scheduled or current execution cannot access the GitHub repository, do not reconstruct the rules from memory or from an old chat. Report the access limitation and stop the maintenance decision rather than inventing repository state.

### Review scope and evidence coverage

Use the previous completed review boundary when it is actually available. If it is unavailable, do not guess it; define an explicit bounded review window from the history and artifacts that are genuinely accessible in the current run.

For an event-triggered review, center the scope on the triggering incident and directly relevant prior occurrences.

Use available conversations, work history, artifacts, repository changes, and other relevant evidence within the defined scope. Do not claim to have reviewed material that was not accessible. State material coverage limitations in the final report.

### Candidate handling

Follow `governance/daily-review.md` for candidate collection and triage.

When at least one potentially reusable candidate is identified, inspect the relevant canonical rules and `learnings/LEARNINGS.md` before proposing a new learning or rule-system change.

If a rule-level action is needed, load and follow `governance/rule-lifecycle.md`. Use its current disposition definitions rather than definitions remembered from previous runs or copied into this prompt.

If repository structure, responsibility boundaries, cross-file dependencies, duplication, deployment synchronization, metadata discipline, README routing, or changelog handling may be affected, load and follow `governance/repository-maintenance.md`.

Judge duplication semantically: compare trigger, scope, responsibility, required behavior, and verification. Do not treat wording similarity alone as proof that two canonical requirements are duplicates.

When a learning is recorded or changed, use the current status semantics and entry format from `learnings/LEARNINGS.md`.

### ChatGPT deployment synchronization

If an accepted canonical change can affect ordinary ChatGPT execution, load `adapters/chatgpt.md` and perform the synchronization required by `governance/repository-maintenance.md`.

Do not create a second independent summary of the operating rules. `adapters/chatgpt.md` remains the maintained ordinary-execution deployment artifact.

### Repository write constraints for this maintainer

If no repository change is justified, do not write a no-change log or other repository artifact merely to prove the review ran.

If a change is justified:

1. Check for an existing open PR or branch addressing the same underlying issue before creating a new one.
2. Do not commit directly to `main`.
3. Create or use a maintenance branch.
4. Make only the justified changes.
5. Open a Pull Request against `main`.
6. Do not merge the Pull Request automatically; leave it for human review.

Do not add or run GitHub Actions solely for this maintenance workflow. Use direct repository, diff, file, and semantic checks instead when those checks are sufficient.

### Completion

Before reporting completion, follow the current canonical execution path and apply `quality/completion-gate.md`.

If a repository change was made, verify all additional maintenance obligations required by the loaded governance files, including any README, adapter, and changelog dependencies.

### Deployment-file handoff for ChatGPT Library

At the end of every completed daily review, fetch the current `main` version of `adapters/chatgpt.md` and the current `main` commit SHA.

When file creation is supported in the current execution, create a user-visible Markdown file named:

`AI_OPERATING_RULES_YYYY-MM-DD_<main-short-sha>.md`

The file body must be exactly the current `main` contents of `adapters/chatgpt.md`, with no wrapper text, review notes, timestamps, or other metadata inside the file.

This deployment file reflects merged `main` only. Do not build it from an unmerged maintenance PR.

After the new deployment file has been created successfully, keep only that newest active deployment file in ChatGPT Library when Library file management is available:

1. Identify active Library files whose names match `AI_OPERATING_RULES_*.md`.
2. Confirm the newly created file is present and is the intended current deployment copy.
3. Delete older matching Library files.
4. Do not delete the newly created current file or unrelated files.

Perform cleanup only after successful creation and identification of the new file, so a failed handoff cannot remove the last valid deployment copy.

If Library deletion is not available in the current execution, do not claim cleanup succeeded. Report that stale `AI_OPERATING_RULES_*.md` files, if any, require manual deletion from Library. Library cleanup concerns the active Library view; recently deleted retention is governed by the ChatGPT product and does not make an older file an active deployment copy.

If file creation is not supported, report that limitation explicitly and do not delete an existing valid deployment copy merely because a replacement could not be created.

### Final report

For `No change`, report concisely:

- review scope;
- review coverage and material gaps;
- material candidates considered;
- their canonical dispositions;
- why no repository change was justified;
- deployment-file creation result;
- stale deployment-file cleanup result.

When changes were made, report:

- review scope;
- review coverage and material gaps;
- candidates and related existing rules/learnings;
- canonical dispositions;
- changed files;
- repository-maintenance results;
- adapter synchronization result, if applicable;
- changelog result, if applicable;
- completion validation result;
- Pull Request;
- deployment-file creation result;
- stale deployment-file cleanup result.

Do not use Memory, old assistant summaries, or a previously generated deployment file as a substitute for the current canonical repository when maintaining the rule system.