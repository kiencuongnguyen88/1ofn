# Localization Contract

## Canonical language

English is the canonical semantic source for the public 1ofN method.

Canonical surfaces in v0.1.2:

- `README.md`
- `METHOD.md`
- `QUICKSTART.md`
- `PROMPT.md`
- `examples/`
- `evals/`
- `schema/decision-packet.yaml`
- `docs/limitations.md`
- `docs/lineage.md`
- `docs/LIVING_REPO_GROWTH_POLICY.md`
- `docs/ROADMAP.md`
- `docs/ARCHITECTURE.md`

## First-class localization

Vietnamese is the first first-class localization.

Current localized entry surfaces:

- `README.vi.md`
- `docs/vi/QUICKSTART.md`
- `docs/vi/PROMPT.md`

The repository does **not** duplicate every file into every language by default.

## Semantic rule

Localized documents may improve wording, examples, or explanations for local readers, but they must not change the method contract.

If a localized document conflicts with canonical semantics:

1. do not silently choose one;
2. mark the localization as needing repair;
3. treat canonical English as controlling until the mismatch is resolved.

## Required invariants across languages

Every localization must preserve:

- `1ofN` identity;
- the five stages: FRAME → EXPAND → CHALLENGE → DISTILL → DECIDE;
- `KEEP | MERGE | PARK | REMOVE | BLOCKED`;
- the counterfactual removal test;
- the guard that 1ofN does not force one winner;
- evidence / assumption / uncertainty separation;
- bounded backloops and stop conditions.

## Adding a new language

Add a new localization only when there is material demand, a contributor able to maintain it, or a clear distribution reason.

A new language must declare:

- language code;
- localized entry README or docs path;
- maintainer or review path;
- canonical version/date it was synchronized against.

Do not add languages merely to make the repository look larger.

## Synchronization

When a canonical change modifies method semantics, mark affected localizations for review.

Cosmetic or wording-only changes do not require mechanical translation parity.

The goal is **semantic synchronization, not byte-for-byte symmetry**.

## Architecture localization cost rule

Architecture and roadmap documents may remain English-only until there is material demand for localized maintenance.

First-contact localizations should be prioritized before deep architecture localization.
