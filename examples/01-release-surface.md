# Worked Case 1 — Choose the Right First Release Surface

## Situation

A creator has developed a new decision method and wants to release it publicly.

Known options:

1. build a web app;
2. build a CLI;
3. publish documentation and examples.

Desired outcome: get real usage evidence quickly without spending weeks building infrastructure that may not matter.

Constraints:

- method is not yet validated by external users;
- implementation time is limited;
- the first release must be understandable without installation.

## 1. FRAME

The real decision is not “Which interface is coolest?”

It is:

> Which first release surface gives people enough value to test the method while preserving the option to build software later?

## 2. EXPAND

Add two candidates:

4. documentation first, then app only if repeated interaction needs appear;
5. interactive spreadsheet/template.

## 3. CHALLENGE

| Candidate | Support | Contrary evidence / failure mode |
|---|---|---|
| Web app | easy guided UX | build cost arrives before method proof; UI may hide reasoning |
| CLI | versionable, developer-friendly | narrow audience; installation adds friction unrelated to method value |
| Docs + examples | fastest path to understanding and reuse | less interactive; relies on user discipline |
| Docs first → app later | preserves speed now and optionality later | requires a clear reopen trigger |
| Spreadsheet/template | structured and accessible | can push the method toward premature scoring |

## 4. DISTILL

- Web app → **PARK**. Material later value, wrong timing now.
- CLI → **REMOVE**. No distinct first-release capability that docs cannot absorb.
- Docs + examples → **KEEP**.
- Docs first → app later → **MERGE** into the selected staged path.
- Spreadsheet/template → **PARK** pending evidence that users need structured manual entry.

## 5. DECIDE

**Selected path:** release documentation, examples, prompt, schema, and evaluation first.

Why it survives:

- directly tests whether the method itself creates value;
- low adoption friction;
- preserves app/CLI optionality;
- produces evidence about what software would actually need to do.

### Reversal condition

Reopen the web app if repeated users struggle with the same interaction sequence or need persistent decision state.

### Next action

Publish a documentation-first candidate and collect three external use cases before choosing a software surface.
