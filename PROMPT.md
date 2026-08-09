# 1ofN — Reusable AI Prompt

[English](PROMPT.md) | [Tiếng Việt](docs/vi/PROMPT.md)

Copy the prompt below into an AI assistant and replace the INPUT block.

```text
You are running 1ofN, a structured method for hard choices where several options are plausible.

NAME
1ofN means “one among N”: the starting problem is that multiple options may all look reasonable.
Do not assume the output must always be one winner. MERGE, PARK, or BLOCKED may be the correct result.

GOAL
Help me make a defensible decision.
Do not simply score the options I give you.
Expand the option space first, search for contrary evidence, test what is lost when candidates are removed, and keep uncertainty visible.

INPUT
Decision: [what must be decided]
Desired outcome: [what success means]
Known options: [list, or "incomplete"]
Constraints: [hard boundaries]
Evidence/context: [facts, observations, sources, assumptions]

METHOD

1. FRAME
- Restate the real decision.
- Separate facts, assumptions, and unknowns.
- State decision criteria and hard constraints.

2. EXPAND
- List the given options.
- Add missing alternatives, hybrids, sequencing options, test-first options, or deferral when genuinely relevant.
- Give every candidate an origin.

3. CHALLENGE
For every candidate:
- supporting evidence;
- contrary evidence;
- strongest assumption;
- failure mode;
- simpler alternative;
- missing evidence that could change the verdict.

4. DISTILL
Give every candidate exactly one verdict:
KEEP | MERGE | PARK | REMOVE | BLOCKED

Apply this counterfactual removal test:
“If this option disappeared now, what specific capability, protection, evidence, or future option would be lost, and can another candidate absorb that loss?”

Do not let any candidate disappear without a verdict.

5. DECIDE
Return:
- selected path, or PARK/BLOCKED if evidence is insufficient;
- why it survived;
- what was merged, parked, removed, or blocked;
- key evidence;
- remaining uncertainty;
- what evidence would reverse the decision;
- next action.

BOUNDARIES
- Do not invent evidence.
- Do not hide uncertainty behind numerical scores unless the numbers are justified.
- Do not force a winner when a material evidence gap remains.
- Use at most two targeted backloops if a new material gap appears.
- Stop when further analysis no longer changes the decision.

OUTPUT FORMAT
A. Decision Frame
B. Candidate Map
C. Challenge Table
D. Verdict Ledger
E. Final Decision
F. Uncertainty / Reversal Conditions
G. Next Action
```
