# Learnings

This file holds reusable failure patterns that have not yet been promoted to canonical rules. It is not a chat log, TODO list, revision history, or archive of every mistake.

Read this file when recording or reviewing a reusable failure pattern, comparing a new candidate with existing learnings, or considering promotion, merge, or retirement.

Before creating a new entry, compare the candidate with existing entries and relevant canonical rules. Update or merge an existing entry when it represents the same underlying failure pattern closely enough that a separate entry would duplicate the learning.

Promote, merge, or retire entries according to `governance/rule-lifecycle.md`.

## Status definitions

Use only the following statuses:

- **candidate** — a potentially reusable failure pattern has been identified, but recurrence or broader applicability has not yet been established.
- **recurring** — the same underlying failure pattern has been observed in at least two distinct occurrences under a compatible trigger or scope.
- **ready-for-promotion** — the pattern is recurring; its trigger, scope, and failure mode are sufficiently defined; a verification approach can be stated; and existing learnings or canonical rules do not adequately absorb it. This status means the learning is ready for a promotion decision under `governance/rule-lifecycle.md`; it does not itself approve promotion.
- **retired** — the entry has been promoted, merged into another learning or rule, found not to be reusable, superseded, or no longer applicable.

Status changes must be supported by the observations recorded in the entry. Do not advance a status merely because time has passed or because a review is being performed.

## Entry template

```md
## Learning: <short name>

**Status:** candidate | recurring | ready-for-promotion | retired  
**Scope:** global | conditional:<trigger> | domain:<domain>

### Observations

- <distinct occurrence and relevant context>
- <additional distinct occurrence when applicable>

### Trigger

<condition that activates the failure mode>

### Failure mode

<what goes wrong>

### Candidate rule

<optional until the pattern is mature enough for rule-level evaluation>

### Verification

<how to check whether a proposed rule would work or was followed; may remain unresolved at candidate stage>

### Related canonical rule

<existing rule or none>

### Related learning

<existing learning that overlaps with or may absorb this entry, or none>

### Promotion decision

<retain as learning, update existing learning, refine existing rule, promote, merge, or retire>
```
