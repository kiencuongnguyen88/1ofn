# 1ofN

[English](README.md) | [Tiếng Việt](README.vi.md)

**When several options all make sense. Decide what deserves to survive.**

Generative AI made producing plausible options cheap. `1ofN` starts where generation stops: when several alternatives can all look reasonable and the hard part is deciding what deserves commitment without silently losing material value.

`1ofN` means **one among N**: you have multiple plausible options, but you still need to determine **what deserves to survive, what should merge, what should wait, what can be removed, and whether the evidence is strong enough to decide at all**.

You only need to understand the name once. After that, `1ofN` is both the name of the problem and the method for resolving it.

> N plausible options → challenge them → reduce the field without losing material value → make a reasoned decision.

**Created by kiencuongnguyen88 (Thầy Cường).** 1ofN grew out of a repeated failure pattern: when several options are individually reasonable, analysing each one more deeply can make *all* of them look stronger without making the actual decision easier. 1ofN exists to turn that ambiguity into an inspectable decision.

## When should you use 1ofN?

Use it when:

- several options are genuinely plausible;
- a simple pros/cons list does not resolve the choice;
- some options may actually overlap or belong in a sequence;
- evidence is mixed with assumptions;
- choosing too early may destroy a better path;
- you need to know **why** an option survived, not just that it received a higher score.

Do not use it for trivial, obvious, low-cost, or easily reversible choices.

## What does 1ofN do?

1. **FRAME** — identify the real decision.
2. **EXPAND** — open the option space before narrowing it.
3. **CHALLENGE** — search for contrary evidence, weak assumptions, and failure modes.
4. **DISTILL** — assign every candidate a visible state: `KEEP | MERGE | PARK | REMOVE | BLOCKED`.
5. **DECIDE** — commit to the strongest surviving path, or state clearly why commitment is premature.

## Full-baseline guard

For a material run, `EXPAND` must not assume the visible options already contain a complete route. 1ofN creates one explicit **FULL_BASELINE** reference before narrowing the field.

The current/incumbent option is not automatically full. If it truly covers the whole decision frame, it can be marked as the baseline after that completeness is checked. `FULL_BASELINE` means complete enough for the material scope, **not maximal complexity**.

A challenger that removes material baseline force should displace it only when the comparison supports **material net advantage** without **material regression**. The baseline is still challengeable; it is a reference, not a forced winner.

See [docs/REPLACEMENT_DECISIONS.md](docs/REPLACEMENT_DECISIONS.md).

## Stable core, living method

`1ofN` is designed to stay easy to recognize even as its execution becomes much stronger.

Four things define its identity:

1. **WHAT** — a specialist method for reducing plausible alternatives without silently losing material value;
2. **PROBLEM** — several options are plausible enough that simple comparison does not reveal what should survive;
3. **WHO / WHEN** — use it when multiple plausible routes materially compete;
4. **HOW** — `FRAME → EXPAND → CHALLENGE → DISTILL → DECIDE`, with the removal test and stable verdict meanings.

The **method stays stable**. Its **capability can improve through cases, evaluation, and learning**. The **tools used to execute it can be replaced as better ones appear**.

That means the first public version can stay simple and low-cost without freezing the method's future.

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) and [docs/ROADMAP.md](docs/ROADMAP.md).

## One important guard

The name `1ofN` **does not mean every run must end with exactly one winner**.

A valid run may end with:

- one selected option;
- several options **MERGED** into a stronger path;
- an option **PARKED** until timing or evidence changes;
- the decision **BLOCKED** because a material evidence gap remains.

`1ofN` names the **starting problem**, not a forced output shape.

## Core verdicts

- **KEEP** — removing it would lose distinct material value that no other candidate absorbs.
- **MERGE** — it contains real value, but that value belongs inside another candidate rather than as a separate path.
- **PARK** — potentially useful, but timing, dependency, or evidence does not justify commitment now.
- **REMOVE** — removing it does not cause material loss to the desired outcome, protection, optionality, or decision quality.
- **BLOCKED** — a missing piece of evidence is important enough that a defensible verdict cannot yet be made.

No candidate is allowed to disappear silently.

## The removal test

A central 1ofN question is:

> **If this option disappeared right now, what would we actually lose that the remaining options cannot absorb?**

If the answer is “nothing material,” the option should not survive just because it sounds sophisticated or attractive.

## Quick start

- [QUICKSTART.md](QUICKSTART.md) — run a case in a few minutes.
- [PROMPT.md](PROMPT.md) — reusable AI prompt.
- [METHOD.md](METHOD.md) — full method contract.

Vietnamese entry points:

- [README.vi.md](README.vi.md)
- [docs/vi/QUICKSTART.md](docs/vi/QUICKSTART.md)
- [docs/vi/PROMPT.md](docs/vi/PROMPT.md)

## Worked cases

- [Choose the right first release surface](examples/01-release-surface.md)
- [Choose how to learn a new technical skill](examples/02-learning-path.md)
- [Choose the next direction for a small product](examples/03-product-direction.md)
- [Choose one primary message for a public launch](examples/04-communication-message.md)

## Decision packet

Machine-readable schema:

[schema/decision-packet.yaml](schema/decision-packet.yaml)

## Evaluation

Do not judge a run by length or by how intelligent the prose sounds. Use:

[evals/rubric.md](evals/rubric.md)

to test whether the run actually improves decision quality.

A focused regression case for incomplete option sets is available at [evals/full-baseline-regression.md](evals/full-baseline-regression.md).

After a decision has produced observable real-world results, you may also use:

[evals/outcome-followup.md](evals/outcome-followup.md)

to preserve the original decision basis, record what actually happened, and identify evidence for future runs. This follow-up is optional: it is not a sixth stage, it does not retroactively rewrite the original decision, and it does not change the five-stage method.

## What 1ofN is not

It is not:

- a scoring formula pretending everything can be quantified;
- an AI oracle that chooses for you;
- a reason to analyse forever;
- a replacement for evidence or domain expertise;
- a mechanism for forcing a decision when material evidence is missing.

See [docs/limitations.md](docs/limitations.md).

## Language model

English is the **canonical language** of the public method. Vietnamese is the first first-class localization.

Localization policy: [docs/LOCALIZATION.md](docs/LOCALIZATION.md)

## License

Current covered non-software repository material is licensed under **CC BY 4.0**.

Preferred attribution: **1ofN by kiencuongnguyen88**

See [LICENSE](LICENSE), [ATTRIBUTION.md](ATTRIBUTION.md), and [docs/LICENSE_SCOPE.md](docs/LICENSE_SCOPE.md).

## Lineage

The public method is independent of the internal system in which its ancestor was first developed. Technical lineage is recorded separately at [docs/lineage.md](docs/lineage.md); users do not need DIAMOND OS or BBR knowledge to use 1ofN.

## Status

`v0.1.3 public release`

Method-first. Documentation-first. No app, package, model, or service is required.
