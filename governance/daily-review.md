# Daily Review

Use this procedure to orchestrate routine daily review of the rule system and event-triggered review after a material incident.

A daily review is a review cadence, not a requirement to modify rules every day. No change is a valid outcome when the reviewed work does not justify a rule-system change.

Do not wait for the next scheduled daily review when a material incident indicates that the rule system may need prompt attention. Run an event-triggered review using this same procedure when there is a significant failure, repeated exception, failed handoff or preservation requirement, material evidence or consistency failure, audit finding, or another issue whose impact makes deferral inappropriate.

Daily review is primarily for candidate triage and diagnosis. Do not treat it as a requirement to search for canonical-rule promotions.

## 1. Define the review scope

Identify the work since the previous review that is relevant to rule quality. For an event-triggered review, define the scope around the triggering incident and any directly relevant prior occurrences.

When selecting candidates, do not over-weight the most recent or salient domain or failure. Consider the relevant work domains and prior occurrences needed to judge whether a pattern is isolated, recurring, or more broadly applicable. Keep event-triggered reviews incident-centered and do not generalize beyond the evidence available from that scope.

Include material failures, repeated friction, incorrect assumptions, preservation failures, weak evidence handling, consistency failures, artifact-quality problems, and rule-maintenance problems.

Do not treat every correction, preference, or isolated wording issue as a rule-system problem.

## 2. Collect reusable candidates

For each potentially reusable issue, record or reconstruct enough context to determine:

- what task or domain was involved;
- what triggered the problem;
- what failed;
- what result should have occurred;
- whether the issue appears isolated or recurring.

Keep transient chat history and unrelated work details out of the rule repository.

## 3. Compare with existing rules and learnings

Before proposing a change or creating a learning entry, inspect the relevant canonical rules and `learnings/LEARNINGS.md`.

Determine whether the issue is already covered, should update or merge into an existing learning, indicates a weakness in an existing rule, is reusable but still immature, or does not justify a rule-system change.

Do not create a new rule or learning merely because a failure occurred.

## 4. Run the applicable maintenance process

For each candidate that requires action, use `governance/rule-lifecycle.md` to choose and apply the rule-level disposition.

If that disposition affects repository structure, responsibility boundaries, cross-file dependencies, duplication, deployment synchronization, metadata discipline, or changelog handling, also apply `governance/repository-maintenance.md`.

Use `learnings/LEARNINGS.md` for reusable patterns that remain below canonical maturity.

## 5. Close the review

After all candidates have been triaged and any justified changes have been made:

1. Confirm that each candidate has a disposition or remains explicitly unresolved for a stated reason.
2. Confirm that any required repository-maintenance work, including deployment synchronization, is complete.
3. Record material semantic or structural changes in `CHANGELOG.md` as required by `governance/repository-maintenance.md`.
4. Apply `quality/completion-gate.md` as the final completion gate for the review.

A scheduled daily review or event-triggered review may therefore end with:

- no repository change required;
- learnings updated only;
- canonical rules updated;
- canonical rules and deployment artifacts updated;
- an unresolved issue kept outside the repository unless it is itself a reusable failure pattern suitable for `learnings/LEARNINGS.md`.

Do not force a rule change to make the review appear productive.
