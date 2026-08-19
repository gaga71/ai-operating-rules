# Learnings

This file primarily holds reusable failure patterns that have not yet been promoted to canonical rules. Retired entries may remain only under the limited retention conditions defined below. It is not a chat log, TODO list, revision history, or archive of every mistake.

Read this file when recording or reviewing a reusable failure pattern, comparing a new candidate with existing learnings, or considering promotion, merge, or retirement.

Before creating a new entry, compare the candidate with existing entries and relevant canonical rules. Update or merge an existing entry when it represents the same underlying failure pattern closely enough that a separate entry would duplicate the learning.

Apply dispositions according to `governance/rule-lifecycle.md`.

## Status definitions

Use only the following statuses:

- **candidate** — a potentially reusable failure pattern has been identified, but recurrence or broader applicability has not yet been established.
- **recurring** — the same underlying failure pattern has been observed in at least two distinct occurrences under a compatible trigger or scope.
- **ready-for-promotion** — the pattern is recurring; its trigger, scope, and failure mode are sufficiently defined; a verification approach can be stated; and existing learnings or canonical rules do not adequately absorb it. This status means the learning is ready for a promotion decision under `governance/rule-lifecycle.md`; it does not itself approve promotion.
- **retired** — the entry has been promoted, merged into another learning or rule, found not to be reusable, superseded, or no longer applicable.

Status changes must be supported by the observations recorded in the entry. Do not advance a status merely because time has passed or because a review is being performed.

After a **Promote** disposition has been implemented and the canonical rule has been accepted, set the learning status to **retired**. After a **Merge** that absorbs the entry elsewhere, or a **Retire** disposition, set the status to **retired** as applicable. Other dispositions do not by themselves imply a status change.

## Candidate review

Retire a candidate when later review shows that it is not sufficiently reusable, has been absorbed by an existing rule or learning, has been superseded, or is no longer useful for active comparison.

Do not retire or delete a candidate solely because a fixed amount of time has passed. Lack of recurrence may inform the judgment, but elapsed time alone is not a disposition rule.

## Retired entries

Retain a retired entry when it is still useful to preserve a promotion or merge decision or to prevent the same learning from being recreated unnecessarily.

A retired entry may be removed when it is no longer needed for active comparison and any material promotion, merge, or retirement history that must be preserved is already recorded in `CHANGELOG.md` or the surviving canonical rule or learning.

Do not keep retired entries solely to turn this file into a permanent failure archive.

## Entry template

```md
## Learning: <short name>

**Status:** candidate | recurring | ready-for-promotion | retired  
**Scope:** global | conditional:<trigger> | domain:<domain> | maintenance:<area>

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

### Disposition

<applicable disposition from governance/rule-lifecycle.md>
```

For a learning entry, the applicable dispositions are normally **No change**, **Learning**, **Refine**, **Narrow**, **Merge**, **Promote**, or **Retire**. **Add** is reserved for direct canonical requirements and is not used to bypass learning maturity for a failure-derived entry.

## Learning: Reuse before invention in design work

**Status:** recurring  
**Scope:** conditional:designing reusable structures or implementations

### Observations

- In one reusable implementation-design task, a proposed structure required correction because established comparable implementations had not been used aggressively enough as the starting point.
- In a later repository-structure task, the same underlying issue recurred: the design needed closer precedent research and less repository-specific invention before settling the structure.

### Trigger

A task requires designing a reusable structure, architecture, workflow, repository layout, skill, or implementation where established prior implementations may provide a suitable basis.

### Failure mode

A plausible structure is designed from first principles too early. This can create avoidable novelty, duplicate established solutions, and make the result harder to justify or maintain even when relevant prior implementations exist.

### Candidate rule

Before materially inventing a reusable structure or implementation, inspect relevant established prior implementations and reusable existing material. Prefer reuse, extension, or faithful adaptation when they fit. Isolate and justify the remainder that genuinely requires new design rather than treating originality as a default objective.

### Verification

For a design that introduces material structure or architecture, verify that relevant prior implementations were considered, that reused elements and genuinely new elements can be distinguished, and that new design is justified by an uncovered requirement rather than by discovery order or convenience. The appropriate search depth and quality threshold remain unresolved and should be refined before promotion.

### Related canonical rule

`governance/rule-lifecycle.md` applies the same reuse-before-invention principle to rule-system maintenance, but no current canonical rule extends it to ordinary design work generally.

### Related learning

none

### Disposition

Learning
