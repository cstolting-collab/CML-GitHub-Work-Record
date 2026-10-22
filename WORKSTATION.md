# Estra Logics — Morning Engineering Workstation

**Purpose:** One durable entry point for GitHub issue repair and CML engineering. This is a task index, not an autonomous executor or a substitute for live verification.

**Start each session:** Read [AI Source](AI_SOURCE.md), [daily rules](standards/DAILY-GITHUB-RULES.md), the latest [journal](journals/), then refresh issue/PR/CI state from GitHub. Never assume this snapshot remains current.

## Morning sequence

1. **Restore state:** Read the latest dated journal and the active task's exact issue, branch, and revision.
2. **Choose one task:** Select GitHub repair or CML development. Keep one controlling operator/chat per task.
3. **Investigate:** Reproduce or inspect evidence; state acceptance criteria before changing code.
4. **Implement safely:** Work on a scoped branch; preserve existing history and unrelated files.
5. **Validate:** Run available checks and label any unexecuted checks **UNVERIFIED**.
6. **Handoff:** Record issue/PR links, commit SHA, observed result, unresolved exceptions, next actor, and next action.

## Work queue (snapshot: 2026-10-20)

| Priority | Workstream | Task | State | Next action |
| --- | --- | --- | --- | --- |
| P0 | Profile presentation | Public profile README may not display because the same-name profile repository is private | **PRIVATE — preserve visibility** | Use curated public portfolio; public account profile configuration requires separate GitHub UI access |
| P1 | GitHub organization | Complete repository documentation/readiness review without modifying private or upstream code | **IN PROGRESS** | Review original public project READMEs and record verified gaps |
| P1 | CML Local Alpha | [Tester feedback #1](https://github.com/cstolting-collab/CML-Local-Alpha/issues/1) | **OPEN; feedback template, no submissions recorded** | Await actual sanitized tester evidence; do not treat the template as a confirmed defect |
| P2 | Issue repair | Select a scoped, reproducible issue in an authorized repository | **READY FOR TRIAGE** | Inspect current issue, source and CI; create a branch only after scope is clear |
| P2 | CML research | Minimal continuity guidance vs. model baseline | **PRIVATE RESEARCH** | Preserve original prompts/renders in private research; design controlled comparisons before changes |

## Public portfolio and account profile

- [Curated public engineering portfolio](PUBLIC_PORTFOLIO.md) — verified public-facing entry point, not the GitHub account profile itself.
- The same-name account profile repository remains **private by deliberate privacy choice**. Do not change visibility. GitHub account profile pins and a separate public profile repository still require supported website controls and explicit approval for any new public repository.
- Keep the workstation's public issue queue free of private issue titles, source, experiment prompts, and unpublished render evidence.

## Project entrances

- [CML Local Alpha](https://github.com/cstolting-collab/CML-Local-Alpha) — public static validator, with documented limits
- [CML Trust](https://github.com/cstolting-collab/CML-Trust) — external observation/evidence notebook
- [Pattern Atlas](https://github.com/cstolting-collab/pattern-atlas) — source-noted relationship mapping
- [Engineering Work Record](https://github.com/cstolting-collab/CML-GitHub-Work-Record) — dated evidence and handoffs
- [Public engineering portfolio](PUBLIC_PORTFOLIO.md) — capabilities, selected projects, and public source links

**Privacy boundary:** This public dashboard does not inventory or disclose private repository source, unpublished experiments, credentials, or personal history. Private tasks remain in their authorized private workspaces.

## Status language

**OBSERVED** = directly checked; **IMPLEMENTED** = changed at an identified revision; **VERIFIED** = specified check passed; **UNVERIFIED** = check not run; **BLOCKED** = dependency or approval missing; **PROPOSAL** = not implemented.

## Handoff template

```text
TASK / ISSUE:
SOURCE REPOSITORY:
AUTHORITATIVE BRANCH + SHA:
INHERITED STATE:
EVIDENCE:
CHANGES MADE:
VALIDATION RUN / NOT RUN:
OPEN EXCEPTIONS:
NEXT ACTOR + SINGLE NEXT ACTION:
HUMAN APPROVAL REQUIRED:
```

**Control principle:** STATE → HANDOFF → OWNERSHIP → VALIDATION → NEXT ACTOR → HUMAN AUTHORITY.
