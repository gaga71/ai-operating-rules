# Daily Review

Use this procedure for routine daily maintenance of the rule system. A daily review does not require a rule change; no change is a valid outcome when the reviewed work does not justify one.

## 1. Define the review scope

Identify the work since the previous review that is relevant to rule quality. Include material failures, repeated friction, incorrect assumptions, preservation failures, weak evidence handling, consistency failures, artifact-quality problems, and rule-maintenance problems.

Do not treat every correction, preference, or isolated wording issue as a rule-system problem.

## 2. Collect candidate failures and learnings

For each potentially reusable issue, record or reconstruct enough context to determine:

- what task or domain was involved;
- what triggered the problem;
- what failed;
- what result should have occurred;
- whether the issue appears isolated or recurring.

Keep transient chat history and unrelated work details out of the rule repository.

## 3. Compare against existing rules

Before proposing a change, inspect the relevant canonical rules and determine which case applies:

- an existing rule already covered the failure but was not followed;
- an existing rule is too broad, narrow, vague, or incomplete;
- two or more existing rules overlap or conflict;
- the failure is reusable but not mature enough for a canonical rule;
- the existing rule set cannot represent the failure adequately;
- no rule-system change is justified.

Do not create a new rule merely because a failure occurred.

## 4. Choose a disposition

Assign each candidate one of the following outcomes:

- **No change** — the existing system is adequate or the issue is not reusable.
- **Learning** — retain the reusable pattern in `learnings/LEARNINGS.md` for further observation.
- **Refine** — clarify an existing rule without changing its intended scope.
- **Narrow** — restrict an over-broad rule to its actual trigger or domain.
- **Merge** — combine overlapping rules or requirements.
- **Promote** — move a sufficiently mature learning into the appropriate canonical file.
- **Retire** — remove or supersede a redundant, obsolete, or harmful rule.

Follow `governance/rule-lifecycle.md` for rule-level decisions.

## 5. Update canonical files when justified

Make only the changes required by the chosen disposition.

Place changes according to responsibility:

- global behavior → `rules/core.md`;
- task-triggered behavior → the relevant file under `rules/`;
- domain-specific behavior → the relevant file under `domains/`;
- completion verification → `quality/completion-gate.md`;
- rule-system maintenance → `governance/`;
- immature reusable patterns → `learnings/LEARNINGS.md`.

Apply `governance/repository-maintenance.md` when a change affects repository structure, responsibility boundaries, duplication, or deployment behavior.

## 6. Synchronize the ChatGPT adapter

For every canonical change that can affect ordinary ChatGPT execution, review `adapters/chatgpt.md`.

- Update the adapter when necessary.
- Keep it self-contained for use without repository retrieval in each chat.
- Preserve the same trigger boundaries, precedence, scope, and substantive requirements as the canonical rules.
- Do not leave the adapter silently stale.

No adapter change is required when the canonical change does not affect deployed ChatGPT behavior.

## 7. Update the changelog when material

Record material semantic or structural changes in `CHANGELOG.md`.

Do not record routine review activity, no-change outcomes, temporary candidates, or insignificant wording edits merely to show that a daily review occurred.

## 8. Validate the update

Before completing the review, verify as applicable:

- the identified failure or learning was handled by the selected disposition;
- no required rule meaning was lost;
- triggers and domain boundaries remain correct;
- precedence has not changed unintentionally;
- conditional or domain-specific rules have not become global without justification;
- duplicated or contradictory canonical rules were not introduced;
- dependent files were re-checked;
- `adapters/chatgpt.md` is synchronized where required;
- the repository contains no unnecessary process metadata from the review itself.

## 9. Complete the review

A daily review is complete when all candidates in the review scope have a disposition and all justified repository changes have been validated.

Possible final states include:

- no repository change required;
- learnings updated only;
- canonical rules updated;
- canonical rules and adapter updated;
- unresolved rule-system issue retained for later review with its uncertainty explicit.

Do not force a rule change to make the review appear productive.
