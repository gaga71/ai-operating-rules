# Rule Lifecycle

Use this process when deciding whether to add, change, refine, narrow, merge, promote, or retire a learning or canonical rule.

Use `governance/daily-review.md` when this work is part of a scheduled daily review or event-triggered review. Use `governance/repository-maintenance.md` when the change affects repository structure or responsibility boundaries, creates cross-file dependency or duplication concerns, affects deployment synchronization, or otherwise meets that file's loading condition.

## 1. Capture

Record a failure pattern only when it is useful beyond the immediate incident. Do not promote every isolated mistake directly into a canonical rule.

Before creating a new learning, compare the candidate with `learnings/LEARNINGS.md` and the relevant canonical rules so that an existing learning or rule is updated, refined, or merged when appropriate.

## 2. Diagnose

For a candidate learning or rule, identify as needed:

- **Trigger** — when the failure occurs.
- **Failure mode** — what goes wrong.
- **Rule** — what behavior would prevent or contain the failure.
- **Verification** — how compliance or prevention can be checked.

Also identify which existing rule or learning, if any, already covers the failure.

## 3. Prefer refinement

When a recurring failure appears, first refine, narrow, or merge an existing rule or learning. Add a new canonical rule only when the existing set cannot represent the failure adequately.

## 4. Promote deliberately

Keep reusable but not yet mature patterns in `learnings/LEARNINGS.md`. Use the status definitions in that file when assessing maturity. Promote a learning only after its trigger, scope, failure mode, and verification are sufficiently defined and canonical treatment is justified.

Place a promoted rule according to its scope:

- global behavior → `rules/core.md`;
- triggered task behavior → the relevant file under `rules/`;
- artifact or domain behavior → the relevant file under `domains/`;
- completion verification → `quality/completion-gate.md`.

## 5. Verify

Before accepting a new or changed canonical rule, check that it:

- addresses the diagnosed failure mode;
- has the intended trigger and scope;
- does not duplicate or contradict higher-priority or related rules;
- preserves intended precedence;
- can be verified in practice.

If the accepted canonical change can affect ordinary ChatGPT execution, complete the adapter-synchronization process in `governance/repository-maintenance.md` before treating the rule change as complete.

## 6. Retire or merge

Remove, merge, or narrow rules that are redundant, obsolete, over-broad, or no longer useful. Update or retire affected learning entries as applicable. Record material semantic changes in `CHANGELOG.md`.

## 7. Periodic review

Periodic reviews must consider all relevant work domains and must not over-weight the most recent or salient domain or failure. Use `governance/daily-review.md` for the scheduled and event-triggered review workflow.
