# Rule Lifecycle

Apply this process when maintaining the rule system.

## 1. Capture

Record a failure pattern only when it is useful beyond the immediate incident. Do not promote every isolated mistake directly into a canonical rule.

## 2. Diagnose

For a candidate learning or rule, identify as needed:

- **Trigger** — when the failure occurs.
- **Failure mode** — what goes wrong.
- **Rule** — what behavior would prevent or contain the failure.
- **Verification** — how compliance or prevention can be checked.

Also identify which existing rule, if any, already covers the failure.

## 3. Prefer refinement

When a recurring failure appears, first refine, narrow, or merge an existing rule. Add a new rule only when the existing set cannot represent the failure adequately.

## 4. Promote deliberately

Keep reusable but not yet mature patterns in `learnings/LEARNINGS.md`. Promote a learning to a canonical rule only when recurrence and applicability justify normalizing it.

Place a promoted rule according to its scope:

- global behavior → `rules/core.md`;
- triggered task behavior → the relevant file under `rules/`;
- artifact or domain behavior → the relevant file under `domains/`;
- completion verification → `quality/completion-gate.md`.

## 5. Verify

Before accepting a new or changed rule, check that it addresses the diagnosed failure mode, has the intended scope, does not duplicate or contradict higher-priority rules, and can be verified in practice.

## 6. Retire or merge

Remove, merge, or narrow rules that are redundant, obsolete, over-broad, or no longer useful. Record material semantic changes in `CHANGELOG.md`.

## 7. Periodic review

Periodic reviews must consider all relevant work domains and must not over-weight the most recent or salient domain or failure.
