# Rule Lifecycle

Use this process when deciding whether to add, change, refine, narrow, merge, promote, or retire a learning or canonical rule.

Use `governance/daily-review.md` when this work is part of a scheduled daily review or event-triggered review. Use `governance/repository-maintenance.md` when the change affects repository structure or responsibility boundaries, creates cross-file dependency or duplication concerns, affects deployment synchronization, or otherwise meets that file's loading condition.

## 1. Identify the change source

A rule-system change may originate from either:

- a reusable failure pattern being evaluated through the learning process; or
- a new authoritative requirement or adopted operating policy that is explicitly intended to become persistent canonical behavior.

Do not treat an isolated failure as a direct canonical requirement merely to bypass the learning process. Do not treat a one-off task instruction as a persistent canonical rule unless the rule-system change itself is intended.

Before creating a new learning or canonical rule, compare the candidate with `learnings/LEARNINGS.md` and the relevant canonical rules so that existing material is refined, narrowed, or merged when appropriate.

## 2. Diagnose or define

For a failure-derived candidate, identify as needed:

- **Trigger** — when the failure occurs.
- **Failure mode** — what goes wrong.
- **Rule** — what behavior would prevent or contain the failure, when a rule is mature enough to propose.
- **Verification** — how compliance or prevention can be checked, when a verification method can be defined.

For a direct canonical requirement, identify:

- the authoritative requirement or adopted policy being represented;
- its intended trigger and scope;
- the required behavior;
- how compliance can be verified.

Also identify which existing rule or learning, if any, already covers the requirement or failure.

## 3. Choose a disposition

Use one of the following dispositions:

- **No change** — the existing system is adequate, or the issue does not justify retention or canonical change.
- **Learning** — create or update a reusable failure pattern in `learnings/LEARNINGS.md` without making it canonical.
- **Add** — create a new canonical rule for a persistent authoritative requirement or adopted operating policy that the existing canonical set cannot represent adequately. Do not use Add to promote an immature failure pattern directly into canonical rules.
- **Refine** — clarify an existing rule or learning without intentionally changing its scope.
- **Narrow** — restrict an over-broad rule or learning to its actual trigger or domain.
- **Merge** — combine overlapping rules or learning entries when separate treatment would duplicate meaning.
- **Promote** — move a sufficiently mature learning into the appropriate canonical rule file.
- **Retire** — remove or supersede a redundant, obsolete, harmful, promoted, merged, or no-longer-applicable rule or learning.

Prefer refinement, narrowing, or merge before Add or Promote when the existing system can represent the requirement or failure adequately.

## 4. Add or promote deliberately

### Direct addition

Use **Add** only when a persistent canonical requirement is already authoritative or has been deliberately adopted as operating policy and does not depend on recurrence of a failure pattern to justify its existence.

Place the new canonical rule according to its scope:

- global behavior → `rules/core.md`;
- triggered task behavior → the relevant file under `rules/`;
- artifact or domain behavior → the relevant file under `domains/`;
- completion verification → `quality/completion-gate.md`.

### Promotion from learning

Keep reusable but not yet mature failure patterns in `learnings/LEARNINGS.md`. Use the status definitions in that file when assessing maturity.

`ready-for-promotion` means that a learning is eligible for a promotion decision; it does not itself approve promotion.

Promote a learning only when canonical treatment is justified after considering existing rules and learnings, and when the trigger, scope, failure mode, intended rule behavior, and verification are sufficiently defined for canonical use.

Place a promoted rule according to the same scope rules used for direct addition above.

## 5. Verify the rule-level decision

Before accepting a new or changed canonical rule, check that it:

- represents the identified authoritative requirement or addresses the diagnosed failure mode;
- has the intended trigger and scope;
- does not duplicate or contradict higher-priority or related rules;
- preserves intended precedence;
- can be verified in practice.

If the accepted canonical change can affect ordinary ChatGPT execution, complete the adapter-synchronization process in `governance/repository-maintenance.md` before treating the rule change as complete.

This rule-level verification is part of maintenance, not a replacement for the final `quality/completion-gate.md` required by the canonical execution path.

## 6. Retire or merge

Remove, merge, or narrow rules that are redundant, obsolete, over-broad, or no longer useful. Update or retire affected learning entries as applicable. Record material semantic changes in `CHANGELOG.md`.

## 7. Periodic review

Periodic reviews must consider all relevant work domains and must not over-weight the most recent or salient domain or failure. Use `governance/daily-review.md` for the scheduled and event-triggered review workflow.
