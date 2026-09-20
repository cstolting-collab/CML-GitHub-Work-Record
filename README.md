# CML GitHub Work Record

> Quiet public record of human-led, AI-assisted GitHub repair work.

**PLEASE VALIDATE ALL GITHUB WORKFLOW.**

Scope · evidence · tests · permissions · CI gates · published state.
Nothing is called complete until it is verified.

## What this repository is

This is a public, evidence-bound record of the GitHub issues and pull requests I actively work on with CML/Fermata and AI assistance. Each tracked pull request receives:

1. A direct source link and exact revision.
2. Its observed public state and evidence limits.
3. An estimated collaboration pie chart.
4. A dated journal with ownership, exceptions and a next-actor handoff.

It is not a personal activity feed, a claim of upstream acceptance, or a claim that an AI acted independently. Private, unpublished, duplicate, or unrelated work stays out.

## Positive Progress

**Building our creative space through visible work — September 19, 2026**

We keep positive results visible alongside the work still in progress. A focused repair, a useful review and an honest test record all belong in the creative and engineering workflow.

| Documented progress | Count | Primary evidence |
| --- | --- | --- |
| **Human reviewer approval** | **1 highlighted** | [CISA #64: Sylvester Kaczmarek approved the revision and resolved his objection](https://github.com/cisagov/gh-skeleton/pull/64#pullrequestreview-5246131633). He also reported the regression and diff check passing. |
| **Favorable automated review** | **1 highlighted** | [Semantic Kernel #14454: Copilot recommended approval](https://github.com/microsoft/semantic-kernel/pull/14454#pullrequestreview-5239082617). Its submitted review state is `COMMENTED`, not `APPROVED`; it is not a human approval. |
| **Contributions with published repair or validation evidence** | **6** | CISA #64, Semantic Kernel #14454, FHIR #5825 and #5829, OpenAI Go #932 and #933. [Read the complete source-linked scorecard](journals/2026-09-19.md#positive-progress). |

These counts overlap: the two review positives belong to the six contributions; they are not eight successes. All six PRs were open and unmerged when inspected, so this is a progress record, not a completed-repair count. Reported tests remain attributed to their reporters, and unfinished tests and blockers remain visible.

**[Read Positive Progress: the six-contribution record, exact revisions and what we carry forward](journals/2026-09-19.md#positive-progress)**

This is a user-authorized retrospective, not an expansion of the three-PR scheduled dashboard below. Existing monitoring assignments, authorization boundaries and outcome-chart scope are unchanged.

> **Progress is worth recording before completion. Completion is worth claiming only when verified.**

## Current PR dashboard

![Current GitHub work outcomes](assets/pr-outcome-grid.svg)

The pie in every card is an **estimated work-contribution allocation**, not time tracking, legal ownership, or a productivity score: **35% human leadership and authority, 40% AI-assisted technical execution, and 25% CML/Fermata integrity method.** Human authorship, approval, and accountability remain mine.

The dashboard is intentionally limited to the three active pull requests currently being monitored. Snapshot: **September 19, 2026**; see the dated journal for observation times, full SHAs and primary workflow links. **FHIR is BLOCKED with a FAILED metadata check and separate CI holds.** The two OpenAI Go cards retain their earlier HOLD snapshots; they were not reverified in the FHIR-only follow-up. None is a completed success.

| Pull request / observed head | Current public state | Evidence record | Source |
| --- | --- | --- | --- |
| Microsoft FHIR Server #5829 · `512dad5` | `OPEN` · unmerged · **BLOCKED: metadata FAILED; CI authorization HOLD** | Current scope is **CA2024 only**; other migration-era suppressions remain. PR reports a Release rebuild with 0 errors and 125 focused tests passed / 10 skipped; the two modified emulator-dependent tests were not executed locally. `license/cla` passed. `Check Metadata` failed because required classification labels and a sprint milestone are missing, including the external-author/work-item condition. Code Scanning remains `action_required`; Azure execution and full required-gate coverage are unestablished. | [PR #5829](https://github.com/microsoft/fhir-server/pull/5829) · [Failed metadata job](https://github.com/microsoft/fhir-server/actions/runs/35417396222/job/105828564360) · [Issue #5679](https://github.com/microsoft/fhir-server/issues/5679) |
| OpenAI Go #932 · `0d11494` | `OPEN` · unmerged · upstream CI hold | Focused regression, vet and diff-check commands are recorded in the PR. Mock-backed endpoint suite was not run because a pinned dependency could not be fetched. Returned upstream Actions runs are `action_required`. No tests were rerun by this record inspection. | [PR #932](https://github.com/openai/openai-go/pull/932) · [Issue #631](https://github.com/openai/openai-go/issues/631) |
| OpenAI Go #933 · `9f7f99d` | `OPEN` · unmerged · upstream CI hold | Focused tests, vet, compile-only, Castiron and diff checks are recorded in the PR; a full-suite pass is not claimed. Returned upstream Actions runs are `action_required`. No tests were rerun by this record inspection. | [PR #933](https://github.com/openai/openai-go/pull/933) · [Issue #644](https://github.com/openai/openai-go/issues/644) |

**Evidence correction:** the earlier FHIR dashboard described a broader remediation and a zero-warning build. Those statements must not be carried onto the current narrowed head. The [September 19 scope correction](journals/2026-09-19.md#evidence-correction--fhir-5829) preserves the reason and sources; the historical September 18 journal remains unchanged.

**CI coverage correction:** direct check-run inspection revealed a failed `pull_request_target` metadata workflow that the `pull_request`-only workflow-list helper omitted. The failure occurred on September 18 at 23:02 EDT and was inspected in the September 19 follow-up; it is not a newly occurring code failure. The [appended correction and handoff](journals/2026-09-19.md#correction--metadata-failure-and-ci-coverage) supersede the earlier FHIR HOLD-only summary. No upstream repair or pipeline execution is claimed.

## CML Continuity Principle

A useful agent system must preserve enough continuity for work to move from one actor to the next without requiring the human to reconstruct the workflow.

**STATE → HANDOFF → OWNERSHIP → VALIDATION → NEXT ACTOR → HUMAN AUTHORITY**

A complete handoff carries inherited state, evidence supporting that state, current ownership, authorization boundaries, completion conditions, the next actor, and required human approvals. In this work record it also carries the exact revision, observation time, next trigger and unresolved exceptions.

The goal is not maximum autonomy. The goal is **durable continuity**.

> **When the human disappears, does the system still know who works next?**

An expected next actor is not a claimed accepted assignment. A saved instruction is not proof that the successor ran. A handoff is not called persisted until the write succeeds and the committed content is read back.

## GitHub Follow Through

The configured hourly coordinator inherits the latest journal, rechecks the three upstream contributions, investigates material changes, prepares evidence-bound repair plans or unsent replies when needed, and preserves a resume-ready handoff. The configured daily evening reporter reconciles that record. These are scheduled reporting roles, not a claim of a continuously running multi-agent service or CML compiler/runtime execution.

**Required coverage:** combine current-head check runs, status contexts and relevant workflow runs, including `pull_request_target` and available pagination. A filtered workflow helper is not complete CI evidence. Track labels, milestone, title/body and new run IDs even when the code SHA is unchanged. Distinguish metadata failures, permission holds and actual code-test failures.

| Responsibility | Owner / next actor | Boundary |
| --- | --- | --- |
| Read evidence, recheck state, classify failures, prepare drafts, retain the handoff | GitHub Follow Through coordinator | Continue within existing authority; no extra 'continue' prompt is needed. |
| Reconcile the daily evidence trail and exceptions | GitHub Continuity Journal reporter | Preserve earlier entries and newer hourly records; verify writes by read-back. |
| Apply repository-owned metadata, authorize upstream CI or accept/reject a contribution | Appropriately authorized upstream maintainer | This is the next required role where supported, not an assignment made by this system. |
| Approve external contributor actions outside the reporting boundary | Sherrie Joseph | No automatic upstream comments, pushes, submissions, reruns, reviews, merges, closures, releases or permission changes. |

Public reporting writes are limited to this README, `journals/YYYY-MM-DD.md`, and the existing `assets/pr-outcome-grid.svg`. Current file SHAs protect updates; conflicts require rereading and reconciliation. A failed write becomes a visible BLOCKED exception with the unsaved packet, not an unreported gap.

The final report contains completed work, its evidence trail, the validation result, unresolved exceptions and only genuine human approval needs. Read the [latest journal](journals/2026-09-19.md) through its appended corrections and dated retrospective before inheriting any earlier handoff.

## Daily journals

- [2026-09-19 — Positive Progress, follow-through restoration, FHIR corrections and next-actor handoffs](journals/2026-09-19.md)
- [2026-09-18 — Initial public record; historical scope, superseded where noted](journals/2026-09-18.md)

## Status rules

Evidence labels and operational decisions are separate.

- `IMPLEMENTED`, `VERIFIED`, `OBSERVED`, `INFERENCE`, `HYPOTHESIS`, `PROPOSAL`, `UNKNOWN` describe evidence status; no silent promotion between them.
- `VERIFIED`, `HOLD`, `FAILED`, `BLOCKED`, `UNKNOWN` describe an operational gate. State what was verified; do not use a single green label to conceal incomplete gates.
- Preserve raw CI outcomes. `action_required` is not a passed or failed code test. Pending, cancelled, skipped and unavailable results are not successful validation. A genuinely failed metadata check remains FAILED even when its correction requires a maintainer.

An open PR is not a completed result. Mergeable is not approved. A passing local test is not upstream acceptance. A closed-unmerged PR is not a successful merge. A merged PR is not automatically a release or production verification.

---

**Human-led. AI-assisted. Evidence-bound.**
