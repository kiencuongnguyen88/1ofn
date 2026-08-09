# 1ofN Living Repo Growth Policy v0.1

## Principle

`1ofN` should be treated as a living specialist repository.

Its growth should follow real demand, not imagination alone.

The first public release should stay easy to use, easy to remember, and low-cost. High long-run potential is not a reason to create high first-use complexity.

## Upgrade trigger

Open an upgrade candidate when at least one is true:

- repeated real cases expose the same failure;
- users repeatedly request the same missing capability;
- a tool materially improves one fixed role;
- an eval repeatedly detects the same weakness;
- third-party implementations create interoperability/governance needs;
- a critical failure shows the current method can silently lose material value.

## Upgrade sequence

```text
NEED
 ↓
EVIDENCE
 ↓
CANDIDATE REPAIR
 ↓
REMOVE TEST
 ↓
EVAL / REGRESSION
 ↓
VERSIONED UPGRADE
```

## Demand classes

### Small demand
Examples:
- documentation ambiguity;
- missing example;
- localized explanation.

Response:
- doc/case repair.

### Repeated execution demand
Examples:
- recurring evidence conflict;
- recurring nested decisions;
- repeated provenance difficulty.

Response:
- capability improvement inside existing roles.

### Tool demand
Examples:
- manual work becomes a repeated bottleneck;
- traceability becomes too expensive;
- many tools need coordination.

Response:
- add or replace execution instruments.

### Ecosystem demand
Examples:
- third-party implementations;
- contributors;
- compatibility claims;
- canonical version disputes.

Response:
- reopen governance/compatibility architecture.

## Anti-bloat rule

Do not add a capability merely because it may be useful someday.

Any addition to canonical 1ofN must answer:

1. What repeated need or critical failure created it?
2. Which existing role owns it?
3. Why can current capability/tools not absorb the need?
4. What is lost if the addition is removed?
5. What eval proves the upgrade?

## Long-horizon position

The repository may become large.

That is acceptable if:
- identity stays narrow;
- growth comes from use;
- each addition has evidence;
- old cases remain interpretable;
- Remove Test remains active on the method itself.
