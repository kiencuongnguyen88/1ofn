# 1ofN Method

[English](METHOD.md) · Canonical method contract

## 1. Purpose

`1ofN` is for **material decisions in which multiple options are plausible enough to compete**.

Use it when the choice can change direction, architecture, priority, ownership, commitment, or resource allocation, and when no option can be eliminated by a simple lookup.

Do not use it for trivial, obvious, low-consequence decisions, or cases where a single missing fact can directly resolve the choice.

---

## 2. Constitutional invariants

Normal version upgrades may deepen execution, but they must not silently change the identity of `1ofN`.

Four things are constitutional:

1. **WHAT** — `1ofN` is a specialist method for reducing plausible alternatives without silently losing material value.
2. **PROBLEM** — it addresses decisions where several alternatives are plausible enough that simple comparison does not reveal what should survive.
3. **WHO / WHEN** — it activates when multiple plausible routes materially compete and the choice can change direction, commitment, or future option space.
4. **HOW** — it reasons through `FRAME → EXPAND → CHALLENGE → DISTILL → DECIDE`, preserves `KEEP | MERGE | PARK | REMOVE | BLOCKED`, and keeps the counterfactual removal test.

A change that materially breaks one of these four should be treated as an **identity-breaking change**, not assumed to be a normal upgrade of the same method.

---

## 3. Fixed spine, elastic depth

The five stages are the stable semantic spine.

Their internal processing may become much stronger over time through:

- better evidence and source handling;
- accumulated real cases;
- stronger evaluation;
- improved dependency and horizon reasoning;
- recursive child runs that use the same five-stage spine;
- better audit, trace, and convergence;
- better execution tools.

A stronger run is **not** defined by more stages or more text. It is defined by better decision quality inside the same roles.

Tools are replaceable instruments. They may strengthen a stage, but they do not redefine stage semantics, verdict meanings, the removal test, or the stop rule.

---

## 4. Decisions are current, not eternal

`1ofN` does not promise a permanently correct choice.

A material decision is conditional on current:

- evidence;
- constraints;
- option space;
- decision horizon;
- reversibility;
- environment.

A later run may legitimately reach a different conclusion when those conditions change.

That is why a strong `DECIDE` output preserves:

- residual uncertainty;
- reversal conditions;
- reopen conditions;
- the evidence basis for the current decision.

---

## 5. Inputs

A strong run starts with as many of the following as possible:

- **Decision** — what actually has to be decided;
- **Desired outcome** — what success means;
- **Known options** — the options currently visible, even if incomplete;
- **Constraints** — boundaries that must not be violated;
- **Evidence** — facts, measurements, observations, sources;
- **Assumptions** — beliefs not yet verified;
- **Decision horizon** — whether the decision is immediate, reversible, or hard to reverse.

If the frame is ambiguous enough to change how the options should be compared, repair the frame before continuing.

---

## 6. Five stages

### Stage 1 — FRAME

Identify the real decision.

Ask:

- What are we actually deciding?
- Which outcome matters most?
- Which constraints are real and which are habits or inherited assumptions?
- If we look several steps ahead, what would success actually mean?
- Which claims are facts, assumptions, and unknowns?

**Output:** a testable decision frame.

**Fail condition:** the candidates are not yet competing inside the same decision.

---

### Stage 2 — EXPAND

Open the option space before narrowing it.

Ask:

- What options already exist?
- Is there a hybrid that absorbs the strengths of two options?
- Are we comparing candidates at different levels?
- Are “do nothing,” “delay,” “test first,” or “A then B” valid candidates?
- Does a hidden dependency create another option?

### Required full baseline

Every material 1ofN run must carry one explicit `FULL_BASELINE` reference before `DISTILL`.

Do not assume the visible options contain a complete route. During `EXPAND`, construct a complete-enough reference candidate from the decision frame:

> If the currently visible options did not constrain us, what route would preserve all material outcome, constraint, protection, dependency, continuity, and future-option value required by this decision?

`FULL_BASELINE != MAXIMAL_COMPLEXITY`. The baseline keeps material force required by the current frame; it does not collect every imaginable feature.

`CURRENT / INCUMBENT != FULL_BASELINE` by default. If a given or current candidate is explicitly shown to satisfy the whole frame, that same candidate may carry the `FULL_BASELINE` role instead of creating a duplicate.

Each candidate gets an origin:

- `GIVEN`
- `EVIDENCE_DERIVED`
- `NEW_ALTERNATIVE`
- `HYBRID`
- `DEFERRED_TEST`
- `SYNTHESIZED_FULL_BASELINE`

**Output:** a candidate map with one explicit full-baseline reference. Nothing is added or removed silently.

---

### Stage 3 — CHALLENGE

Try to make every candidate fail before trusting it.

For each candidate ask:

- What evidence supports it?
- What evidence argues against it?
- Which assumption carries the most weight?
- Which failure mode would turn it into a bad choice?
- Is the evidence fresh enough?
- Is there a simpler option that preserves the same value?
- Is the candidate attractive because it is useful, or because it sounds sophisticated?

### Baseline / challenger check

Challenge the full baseline too. It is a reference, not an automatic winner.

For any challenger that removes, skips, reorders, shadows, or replaces material baseline force, ask:

- What material net advantage does the challenger create?
- What material capability, protection, evidence quality, continuity, recovery, or future option regresses?
- Can the challenger absorb that loss another way?
- Is the challenger attractive because it is newer, shorter, cheaper on the first pass, or more elegant rather than because it is better for the actual decision?

A challenger should displace material baseline force only when the comparison supports both **material net advantage** and **no material regression**.

When cost is decision-relevant, compare the expected path to a valid outcome across the whole loop, not first-pass cost alone. Relevant factors may include gap repair, retry, escalation, decision-maker attention, rework, switching, assurance, recovery, downstream omission/failure, and opportunity cost.

If calibration is weak, use qualitative dominance. Do not invent probabilities or weighted scores.

A candidate that has not faced contrary evidence is not ready for a terminal verdict.

**Output:** supporting evidence, contradictions, failure modes, missing evidence, and the baseline/challenger comparison where material.

---

### Stage 4 — DISTILL

Reduce the field without losing material capability.

Every candidate receives exactly one provisional verdict:

#### KEEP
Removing it would lose distinct material value that no other candidate absorbs.

#### MERGE
It contains real value, but that value belongs inside another candidate rather than as an independent path.

#### PARK
It may become useful, but timing, dependency, or current evidence does not justify commitment now.

#### REMOVE
Removing it does not materially damage the outcome, protection, optionality, or decision quality.

#### BLOCKED
The verdict depends on missing evidence that is important enough to change the decision.

### Counterfactual removal test

Ask for every candidate:

> **If this option disappeared right now, what specific capability, protection, evidence, or future option would be lost — and can another candidate absorb that loss?**

If nothing material is lost, the candidate does not survive merely because it is “also good.”

When a candidate would replace, supersede, simplify away, or merge away material baseline/incumbent force, also check:

- which upstream or downstream dependency changes;
- which durable capability or protection must remain;
- continuity and reconstructability;
- switching, rework, assurance, recovery, or rollback needs when material;
- new failure modes and blast radius.

The goal is not to preserve an old implementation for its own sake. The goal is to preserve material value unless evidence supports a better replacement.

**Output:** a complete verdict ledger, including material value-retention effects where replacement is involved.

---

### Stage 5 — DECIDE

Commit to the strongest surviving path — or explicitly decline to commit.

The final decision must include:

- selected path;
- the explicit full-baseline reference;
- why the selected path survived against the relevant baseline and challengers;
- what was merged, parked, removed, or blocked;
- key evidence;
- expected-valid-outcome / whole-loop-cost basis when material;
- residual uncertainty;
- reversal conditions;
- the next action or next evidence-gathering test;
- if the decision maker intentionally chooses a different action from the analytical result, record that choice separately without relabeling the analytical winner.

`PARK` and `BLOCKED` are valid results. `1ofN` does not force false certainty.

---

## 7. Backloop rule

Do not restart the entire method because one gap appears.

Allow at most two targeted backloops when:

- decisive evidence is missing;
- a hidden option appears;
- a new contradiction changes a verdict;
- counterfactual loss is unclear;
- challenge reveals a simpler alternative.

Return only to the stage that needs repair.

If a material gap remains unresolved after the necessary backloops, return `BLOCKED` with the exact missing evidence.

---

## 8. Stop rule

Stop when:

- the option space has been sufficiently scanned;
- one explicit `FULL_BASELINE` reference has been constructed or proven from an existing candidate;
- no material candidate has disappeared silently;
- contrary evidence has been tested;
- verdicts are stable;
- further analysis no longer changes the decision;
- remaining uncertainty is visible and acceptable.

Beyond this point, more analysis is more likely to become decision avoidance than decision quality.

---

## 9. Decision quality standard

A strong run lets a reviewer answer five questions:

1. What is the real decision?
2. Which credible alternatives were considered, and what explicit full baseline were they compared against?
3. Why did every rejected option leave the active set?
4. What evidence could reverse the answer?
5. What happens next?

If these five answers are not visible, the run is not complete.
