# Daily GitHub Rules

These rules govern the daily GitHub record and any AI agent working from this repository.

## 1. Evidence before statement

Do not state that work is complete, merged, released, accepted, deployed, fixed, faster, verified, or reproduced unless the relevant repository evidence has been inspected.

Use exact evidence when available:
- repository and branch
- commit SHA
- pull request or issue number
- workflow run and job result
- test result
- benchmark artifact
- dated source record

If the evidence is missing, label the state `UNKNOWN`, `UNVERIFIED`, or `HOLD`.

## 2. Never promote an inference into a fact

Keep these categories separate:

- `IMPLEMENTED` — code or artifact exists at an identified revision.
- `VERIFIED` — the stated check was actually run against the identified revision and passed.
- `OBSERVED` — directly seen in a source or execution result.
- `INFERENCE` — reasoned from evidence but not directly established.
- `HYPOTHESIS` — proposed explanation still requiring a test.
- `PROPOSAL` — suggested future action.
- `UNKNOWN` — not established.

A new agent must not silently upgrade one category into another.

## 3. Preserve acceptance gates

If a benchmark or experiment is `HOLD`, `FAILED`, or `BLOCKED`, it stays there until the exact acceptance condition passes.

Do not:
- relax a threshold to obtain a pass;
- substitute a different metric;
- treat a diagnostic run as an acceptance run;
- treat correctness parity as a performance pass;
- rerun repeatedly without first identifying what the previous result failed to explain.

## 4. Public and private work stay separate

This repository is public.

Never publish:
- credentials, tokens, account identifiers, or secrets;
- private repository contents;
- unpublished source code or patches unless specifically authorized;
- private experiment trees, local paths, private benchmark artifacts, or private model outputs;
- personal information not already intentionally public.

Public summaries may state that private evidence exists only when doing so is necessary and authorized. They must not expose the private contents.

## 5. Read current state before acting

Before modifying a project:

1. read the repository landing page;
2. read the latest dated journal;
3. inspect the current branch / PR / issue / workflow state relevant to the task;
4. identify the authoritative revision;
5. identify the acceptance condition;
6. identify the next actor and human-authority boundary.

Do not continue from memory alone when current repository state is available.

## 6. One authoritative state

For active technical work, record:

`STATE → HANDOFF → OWNERSHIP → VALIDATION → NEXT ACTOR → HUMAN AUTHORITY`

A handoff must preserve:
- accepted state;
- supporting evidence;
- exact revision;
- current owner;
- authorization boundary;
- completion condition;
- unresolved exceptions;
- next trigger;
- next actor.

The next agent must not require reconstruction from chat history when this record already exists.

## 7. Corrections are first-class records

If an earlier AI answer, journal entry, or status statement is wrong or incomplete:

- do not erase the historical fact that it occurred;
- add a dated correction;
- state what was wrong;
- state what evidence corrected it;
- state the new authoritative status.

A correction replaces the conclusion, not the historical record.

## 8. No fabricated continuity

Never invent:
- a command that was not run;
- a file that was not inspected;
- a test result;
- a PR or merge state;
- a benchmark result;
- a timing number;
- a reviewer result;
- a GitHub action;
- a user's approval.

If an action failed, record the failure.

## 9. Daily journal rule

At the end of each working day, create or update `journals/YYYY-MM-DD.md` from verified GitHub activity for that date.

The journal should contain only what can be supported from GitHub or explicitly identified user-provided evidence.

Minimum sections:

```text
# YYYY-MM-DD

## Verified changes
## Tests / workflows / benchmarks
## Holds / failures / blocked items
## Corrections
## Decisions and human authority
## Unresolved questions
## Next concrete step
```

If there was no verified GitHub activity, say so. Do not manufacture a progress entry.

## 10. Morning readback rule

Before new work begins, read:
- `AI_SOURCE.md`;
- this file;
- the latest dated journal;
- the active repository / PR / issue state relevant to the task.

The morning readback must identify:
- what is authoritative;
- what remains unverified;
- what is blocked;
- the next concrete step.

## 11. Terminal-work rule

For interactive terminal work, give one command at a time unless a multi-command block is explicitly requested.

After each command:
1. read the actual output;
2. update the working state;
3. give the next command.

Do not skip failed output or continue as if a command passed.

## 12. Final rule

When evidence and memory conflict, evidence wins.

When two sources conflict, stop and resolve the conflict before changing the authoritative state.

When uncertain, say `UNKNOWN` and specify the exact check needed to resolve it.
