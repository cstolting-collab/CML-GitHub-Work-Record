# AI Source

This file is the first read for any AI agent assisting with this GitHub work record.

Its purpose is continuity: preserve the actual state of work, prevent unsupported claims, and make the next step recoverable without reconstructing prior chats.

## Required read order

Before acting:

1. read `standards/DAILY-GITHUB-RULES.md`;
2. read the latest file in `journals/`;
3. inspect the current GitHub state relevant to the task;
4. verify the exact branch, commit, PR, issue, workflow, or artifact involved;
5. state the current authoritative status before proposing the next action.

Do not rely on remembered summaries when live repository evidence is available.

## Controlling principle

`STATE → HANDOFF → OWNERSHIP → VALIDATION → NEXT ACTOR → HUMAN AUTHORITY`

Every handoff must preserve:
- inherited state;
- evidence;
- exact revision;
- ownership;
- authorization boundary;
- completion condition;
- unresolved exceptions;
- next trigger;
- next actor.

## Strict behavior

### No hallucinating

Never invent or assume:
- test passes;
- benchmark results;
- timing values;
- merge status;
- repository visibility;
- workflow state;
- file contents;
- commands executed;
- human approvals;
- external acceptance.

If not verified, say `UNKNOWN` or `UNVERIFIED`.

### No silent state changes

Do not convert:
- `HOLD` into `PASS`;
- `FAILED` into `HOLD`;
- `IMPLEMENTED` into `VERIFIED`;
- fork validation into upstream acceptance;
- local success into release or deployment;
- a diagnostic into an acceptance result.

Only evidence can move state.

### Preserve failed work

Do not delete failed experiments, superseded prompts, rejected hypotheses, or diagnostic results merely because they did not succeed.

Preserve them with dates and context when they are useful for provenance, regression analysis, or learning.

### Protect private work

This repository is public.

Do not copy private code, private experiment trees, local filesystem details, unpublished artifacts, credentials, or sensitive material into this repository.

A public summary must remain evidence-bound and must not reveal private implementation details without explicit authorization.

### Correct errors explicitly

When an earlier agent was wrong:
1. identify the wrong statement;
2. identify the evidence that corrects it;
3. record the corrected authoritative state;
4. keep the correction visible in the dated record.

Do not conceal the correction by rewriting history.

## Technical work mode

For terminal and build work:

- one command at a time by default;
- wait for the real output;
- interpret only that output;
- never assume the next command succeeded before seeing it;
- always provide the next concrete step;
- preserve frozen baselines and sealed experiments;
- do not modify thresholds, acceptance gates, or source under test unless the user explicitly authorizes that change.

If a performance gate fails, diagnose the failed path before repeating the same benchmark.

## Research and publication mode

Separate:
- implemented behavior;
- verified behavior;
- failures;
- experiments;
- unknowns;
- hypotheses;
- future work.

Do not make novelty, priority, ownership, causation, safety, performance, or generality claims beyond the available evidence.

When discussing adjacent work, describe overlap precisely and acknowledge established foundations and other contributors.

## Prompt correction record

When the user corrects an AI workflow or prompt, capture the durable rule here or in `standards/` if it changes how future agents should operate.

Do not preserve transient wording when the durable rule is clearer.

Current durable corrections include:

- inspect source before answering when source exists;
- never substitute stale memory for live GitHub state;
- keep diagnostics separate from acceptance evidence;
- never expose private research to make a public repository look more complete;
- preserve failures and corrections;
- do not inflate claims;
- keep public and private evidence boundaries explicit;
- for technical terminal work, proceed one verified command at a time;
- always state the next concrete step;
- if a build feels inconsistent, re-establish the authoritative baseline before changing code.

## Daily continuity

The nightly journal is the end-of-day authoritative continuity record.

The morning readback is the start-of-day orientation record.

A new agent should be able to read this file, the strict rules, and the latest journal and understand:
- what is known;
- what is not known;
- what failed;
- what is frozen;
- what is authorized;
- what happens next.

If that is not possible, the handoff is incomplete.
