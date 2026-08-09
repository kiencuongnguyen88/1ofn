# 1ofN — Quick Start

[English](QUICKSTART.md) | [Tiếng Việt](docs/vi/QUICKSTART.md)

Use 1ofN when several options are plausible and you do not know which one actually deserves commitment.

## What the name means

`1ofN` = **one among N**.

Understand the name once. The method then answers:

> Among N competing options, what should survive, what should merge, what should wait, what can be removed, and is the evidence strong enough to decide?

## 60-second setup

Write five lines:

```text
Decision:
Desired outcome:
Known options:
Constraints:
Evidence / context:
```

It is fine if the option list is incomplete. EXPAND exists to find what is missing.

## Run five stages

### 1. FRAME
Rewrite the question as the real decision.

### 2. EXPAND
Add missing alternatives, hybrids, sequencing options, “test first,” or “do nothing for now” when genuinely relevant.

### 3. CHALLENGE
For every candidate, identify:

- supporting evidence;
- contrary evidence;
- strongest assumption;
- failure mode;
- simpler alternative.

### 4. DISTILL
Assign every candidate:

`KEEP | MERGE | PARK | REMOVE | BLOCKED`

Use the removal test:

> If this option disappeared, what material value would actually be lost?

### 5. DECIDE
Return:

- the selected path, or PARK/BLOCKED;
- why;
- remaining uncertainty;
- reversal conditions;
- next action.

## Guard

`1ofN` **does not require one unique winner**.

If two options should become one path → `MERGE`.

If the timing is wrong → `PARK`.

If material evidence is missing → `BLOCKED`.

## Small example

**Decision:** How should a new method be released first?

Options:

- web app;
- CLI;
- documentation + examples.

EXPAND adds:

- documentation first, app only if repeated interaction needs appear.

After CHALLENGE + removal test:

- Web app → `PARK`
- CLI → `REMOVE`
- Docs + examples → `KEEP`
- Docs first → app later → `MERGE` into the staged path

**Decision:** release documentation + examples first; reopen the app only when usage evidence shows a repeated interaction need.

## Reusable prompt

See [PROMPT.md](PROMPT.md).
