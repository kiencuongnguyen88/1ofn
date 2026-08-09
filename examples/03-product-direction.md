# Worked Case 3 — Choose the Next Direction for a Small Product

## Situation

A small product already works for early users. The creator has three competing priorities:

1. add more features;
2. improve reliability and clarity;
3. publish a broader beta now.

Desired outcome: learn from real users without damaging trust or spending months polishing invisible details.

Constraints:

- core workflow is usable but has a few known rough edges;
- feature requests are numerous and inconsistent;
- current user volume is small.

## 1. FRAME

The real decision is:

> What next move maximizes learning from real use while keeping the core experience trustworthy enough to learn from?

## 2. EXPAND

Add:

4. bounded reliability pass → broader beta;
5. invite-only beta with no new features.

## 3. CHALLENGE

| Candidate | Support | Contrary evidence / failure mode |
|---|---|---|
| More features | may attract more users | can increase surface area before current value is understood |
| Reliability/clarity only | strengthens trust | risks polishing indefinitely without new evidence |
| Broad beta now | fastest external learning | noisy defects can contaminate feedback |
| Bounded reliability → beta | balances trust and learning | needs a hard stop to prevent endless polishing |
| Invite-only beta | controlled evidence | may be too small to reveal broader usage patterns |

## 4. DISTILL

- More features → **REMOVE** for this cycle. No evidence that breadth is the current bottleneck.
- Reliability/clarity only → **MERGE** into a bounded pre-beta pass.
- Broad beta now → **MERGE** after the bounded pass.
- Bounded reliability → beta → **KEEP**.
- Invite-only beta → **PARK** as fallback if broad beta risk proves too high.

## 5. DECIDE

**Selected path:** fix only known issues that materially distort the core workflow, then open the broader beta.

Why it survives:

- preserves external learning;
- prevents uncontrolled feature expansion;
- gives reliability work a stopping condition;
- keeps the next product decision evidence-driven.

### Reversal condition

If the bounded reliability pass reveals a core workflow failure rather than rough edges, delay the beta and reopen the product architecture decision.

### Next action

Write a short list of beta-blocking defects, fix only those, then publish the beta and observe usage.
