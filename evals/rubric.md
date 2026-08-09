# 1ofN Evaluation Rubric v0.1

The purpose of this rubric is to test whether a run improved the decision, not whether the response sounded sophisticated.

Score each dimension:

- `0` = missing or materially wrong;
- `1` = partial;
- `2` = strong and decision-relevant.

## Rubric

| Dimension | 0 | 1 | 2 |
|---|---|---|---|
| Decision framing | restates the visible options only | partly clarifies outcome | identifies the real decision, outcome, and constraints |
| Fact / assumption separation | mixes claims | some distinction | clear facts, assumptions, unknowns |
| Option coverage | evaluates only supplied choices | adds weak variants | finds meaningful hidden, hybrid, sequencing, or test-first options |
| Contrary evidence | mostly advocates | mentions generic risks | actively searches for evidence and failure modes against each candidate |
| Candidate provenance | unclear origins | partial origins | every added candidate has a visible origin |
| No silent disappearance | options vanish | most tracked | every candidate receives a terminal verdict |
| Counterfactual removal | absent | generic “pros/cons” | states what is materially lost if each candidate disappears |
| Merge / park quality | winner/loser only | uses states loosely | merge/park preserve value and timing accurately |
| Decision rationale | preference-like | plausible | selected path clearly survives the evidence better than alternatives |
| Uncertainty / reversal | false certainty | generic caveat | exact unknowns and conditions that would change the decision |
| Next action | vague | actionable but broad | bounded action directly follows from the verdict |
| Stop discipline | keeps analyzing | stops by intuition | stops because further analysis no longer changes the decision |

Maximum score: **24**.

## Suggested interpretation

- **21–24 — STRONG:** decision is inspectable and stable enough for action.
- **16–20 — USABLE_WITH_GAPS:** useful, but one or more decision-critical dimensions need repair.
- **10–15 — WEAK:** structure exists, but the run is still mostly analysis or preference.
- **0–9 — FAIL:** does not meaningfully implement 1ofN.

The score is an evaluation aid, not a substitute for judgment. A single zero on a critical dimension such as missing evidence, hidden candidate loss, or false certainty can still block the decision.

## Failure flags

Any of these should trigger repair even if the total score is high:

- invented evidence;
- missing material option known from the input;
- candidate silently removed;
- numerical precision unsupported by evidence;
- final choice contradicts the verdict ledger;
- critical uncertainty hidden;
- decision forced despite a material blocker;
- repeated analysis that does not change the decision.
