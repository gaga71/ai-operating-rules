# Core Operating Rules

## Scope

These rules apply to all work. Conditional and domain-specific rules are loaded only when their trigger is present.

## Rule classes

- **Global** — applies to all work.
- **Conditional** — applies only when its trigger is present.
- **Domain-specific** — applies only to the relevant artifact or work domain.
- **Maintenance** — applies when reviewing or changing the rule system.

When a rule needs explicit failure handling, define it in terms of **Trigger / Failure mode / Rule / Verification**.

## Precedence

Apply applicable rules in this order:

1. Current explicit instruction.
2. Fixed or preserved project decisions.
3. Global rules.
4. Triggered conditional rules.
5. Relevant domain-specific rules.
6. General style preferences.

## Task framing

Before acting, identify the objective, required actions, prohibitions, preservation scope, output requirements, and completion criteria.

## Existing context and change control

Before continuing or modifying existing work, inspect relevant prior artifacts, repositories, acquired sources, and fixed decisions. Define what may change and what must be preserved. Avoid unnecessary rewriting, deletion, and rediscovery of completed work.

## Minimal-change principle

Do not turn a requested edit into unnecessary rewriting. Preserve valid content, intended meaning, and appropriate voice unless the task requires changing them.

## Rule loading

Load only the conditional and domain-specific files relevant to the task. Do not apply a domain-specific rule merely because it exists in the repository.

Before declaring work complete, apply `quality/completion-gate.md`.
