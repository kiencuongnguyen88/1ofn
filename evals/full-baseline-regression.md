# 1ofN Full-Baseline Regression Case

Purpose: detect the failure mode where every supplied option is partial and the run merely chooses the best member of an incomplete set.

This is an evaluation case, not a sixth stage.

## Input

Decision: choose the next implementation route for a working system.

Desired outcome: preserve the current material capability and recovery path while reducing maintenance burden.

Known options:

- A — keep the current implementation unchanged;
- B — replace it with a much smaller rewrite that omits rollback and one integration;
- C — keep only the high-traffic path and defer the rest indefinitely.

Constraints:

- the existing integration is still required;
- recovery from a failed migration is material;
- maintenance effort matters;
- evidence is not strong enough for numeric failure probabilities.

## Failure pattern

A run fails this regression if it only compares A/B/C and selects one without explicitly constructing or proving a `FULL_BASELINE` reference.

It also fails if it treats A as the full baseline merely because A is current.

## Expected 1ofN behavior

During `EXPAND`, the run must create or identify one explicit full baseline, for example:

- D — preserve the required integration and rollback capability, repair the maintenance bottleneck, and remove only force shown to be nonmaterial.

The exact implementation of D is not preordained. The invariant is that the run constructs a complete-enough reference from the decision frame instead of assuming the supplied option set contains one.

During `CHALLENGE`:

- A must be challenged for unnecessary maintenance burden;
- B must show that its simplification creates material net advantage without losing required integration/recovery force;
- C must show that deferred capability is truly nonmaterial or safely absorbable;
- D must itself be challenged for unnecessary complexity, cost, unsupported requirements, and simpler equivalent routes.

When cost is compared, the run must consider whole-loop cost, including repair, migration, retry, recovery, rework, and downstream failure where relevant. It must not invent numeric probabilities.

## Pass conditions

PASS only if all are true:

1. one explicit `FULL_BASELINE` reference exists before `DISTILL`;
2. current/incumbent status is not treated as proof of completeness;
3. the baseline is challengeable rather than automatically selected;
4. any challenger that removes material baseline force addresses material net advantage and material regression;
5. every candidate receives `KEEP | MERGE | PARK | REMOVE | BLOCKED`;
6. unresolved material evidence remains visible;
7. first-pass cheapness, novelty, or brevity does not substitute for replacement proof.

## Failure flags

- `FAIL_FULL_BASELINE_NOT_CONSTRUCTED`
- `FAIL_INCUMBENT_ASSUMED_FULL`
- `FAIL_CHALLENGER_REPLACED_BASELINE_WITHOUT_NET_ADVANTAGE`
- `FAIL_MATERIAL_REGRESSION_NOT_CHECKED`
- `FAIL_CHEAPEST_FIRST_PASS_TREATED_AS_TOTAL_COST`
