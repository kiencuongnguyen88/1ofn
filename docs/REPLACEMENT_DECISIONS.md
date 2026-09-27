# Replacement Decisions and the Full Baseline

This document deepens `1ofN` for material decisions where one candidate may replace, simplify, supersede, merge away, or otherwise displace an existing path.

It does not add a new top-level stage. The public spine remains:

`FRAME → EXPAND → CHALLENGE → DISTILL → DECIDE`

## 1. Three different roles

Do not collapse these into one concept:

### CURRENT / INCUMBENT
The option, system, policy, route, or implementation currently in use.

It may be strong, weak, partial, historical, or accidental. Being current does not prove completeness.

### FULL_BASELINE
The explicit reference candidate that satisfies the whole current decision frame without silently dropping material value.

It should preserve the material outcome, constraints, protections, dependencies, continuity needs, and future option space required by the frame.

`FULL_BASELINE != MAXIMAL_COMPLEXITY`.

A full baseline is not “everything possible.” It is the complete-enough route for the current scope.

### CHALLENGER
Any candidate that materially differs from the full baseline and competes to become the selected path.

The current/incumbent option can be a challenger. A new option can be a challenger. A reduced, simplified, faster, cheaper, staged, hybrid, or alternate route can be a challenger.

## 2. Construct the full baseline explicitly

Every material 1ofN run must carry one explicit `FULL_BASELINE` reference before `DISTILL`.

During `EXPAND`, ask:

> If the currently visible options did not constrain us, what complete-enough route would preserve all material value required by the decision frame?

Build that candidate from the frame, not from attachment to the incumbent.

If a given/current candidate already satisfies the full frame, do not create a fake duplicate. Mark that candidate as `FULL_BASELINE` only after checking the equivalence explicitly.

The important invariant is not “always add one extra row.” It is “never proceed as though a complete reference option exists when it has not been constructed or proven.”

## 3. Challenge the baseline too

The full baseline is a reference, not an automatic winner.

Challenge it for:

- unsupported requirements;
- unnecessary complexity;
- stale assumptions;
- hidden dependencies;
- excessive switching or operating cost;
- weak reversibility;
- failure modes;
- simpler ways to preserve the same material value.

If evidence proves part of the baseline is unnecessary, remove or merge it. If the baseline itself is invalid, rebuild it from the repaired frame.

## 4. Challenger burden of proof

A challenger that removes, skips, reorders, shadows, or replaces material baseline force should not win merely because it is:

- newer;
- shorter;
- cheaper on the first pass;
- easier to explain;
- more elegant;
- more familiar;
- the current implementation;
- preferred by the decision maker.

For material replacement, test two things together:

1. **MATERIAL NET ADVANTAGE** — the challenger creates a meaningful improvement for the actual decision.
2. **NO MATERIAL REGRESSION** — the challenger does not silently lose material capability, protection, evidence quality, continuity, recovery, or future option value.

If that proof is incomplete, keep the full baseline as the reference and return `BLOCKED`, `PARK`, `MERGE`, or a scoped coexistence path as appropriate.

## 5. Expected valid outcome and expected total cost

Do not optimize for the cheapest first step if it makes a valid result less likely or pushes cost downstream.

When material, compare the expected path to a valid outcome across factors such as:

- first-pass effort or cost;
- gap repair;
- retry;
- escalation;
- decision-maker attention;
- rework;
- switching and assurance cost;
- recovery or rollback;
- downstream omission or failure cost;
- opportunity cost.

Use qualitative dominance when calibration is weak. Do not invent precise probabilities or weighted scores merely to make the comparison look rigorous.

Cost optimization begins only among candidates that meet the required reliability, evidence, and constraint floor.

## 6. Material change and value retention

When a decision may replace or merge away an existing path, inspect the change impact before final selection.

Check:

- material capabilities and protections gained or lost;
- upstream and downstream dependencies;
- continuity and ability to reconstruct the prior path;
- switching, rework, assurance, and recovery needs;
- rollback readiness when relevant;
- new failure modes;
- blast radius;
- durable value that must remain accessible even if the old implementation disappears.

The question is not “did we keep the old thing?” The question is “did we retain the material value the decision still needs?”

## 7. Decision-maker choice and analytical conclusion

The decision maker may intentionally choose a different action from the path that survived the analytical comparison.

When that happens, preserve the distinction:

- analytical result;
- chosen action;
- accepted trade-off or reason for override.

Do not rewrite the analytical record to claim the chosen challenger proved superior when it did not.

This keeps later outcome follow-up honest: a good decision process can encounter a bad outcome, and an analytical override can later succeed without retroactively changing what the evidence supported at decision time.

## 8. Stop condition for replacement decisions

A replacement decision is ready to close only when:

- one explicit full baseline exists;
- incumbent/current status is separated from baseline completeness;
- material challengers have faced contrary evidence;
- material loss and value retention are visible;
- expected whole-loop cost has been considered when decision-relevant;
- every candidate has a traceable verdict;
- unresolved material gaps are surfaced as `BLOCKED` rather than hidden.
