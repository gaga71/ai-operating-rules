# Learnings

This file holds reusable failure patterns that have not yet been promoted to canonical rules. It is not a chat log, TODO list, revision history, or archive of every mistake.

Promote or retire entries according to `governance/rule-lifecycle.md`.

## Entry template

```md
## Learning: <short name>

**Status:** candidate | recurring | ready-for-promotion | retired  
**Scope:** global | conditional:<trigger> | domain:<domain>  
**Observed:** <where or under what conditions the pattern was observed>

### Trigger

<condition that activates the failure mode>

### Failure mode

<what goes wrong>

### Candidate rule

<minimal rule that would address the failure>

### Verification

<how to check whether the rule works or was followed>

### Related canonical rule

<existing rule or none>

### Promotion decision

<retain as learning, refine existing rule, promote, merge, or retire>
```

No learning entries are added in the initial repository migration; the existing ten-rule set is being reorganized rather than treated as a set of newly observed candidate learnings.
