# CML GitHub Work Record

> Quiet public record of human-led, AI-assisted GitHub repair work.

**PLEASE VALIDATE ALL GITHUB WORKFLOW.**

Scope · evidence · tests · permissions · CI gates · published state.
Nothing is called complete until it is verified.

## What this repository is

This is a public, evidence-bound record of the GitHub issues and pull requests I actively work on with CML/Fermata and AI assistance. Each tracked pull request receives:

1. A direct source link.
2. Its current public state.
3. An estimated collaboration pie chart.
4. A dated journal entry when material evidence changes.

It is not a personal activity feed, a claim of upstream acceptance, or a claim that an AI acted independently. Private, unpublished, duplicate, or unrelated work stays out.

## Current PR dashboard

![Current GitHub work outcomes](assets/pr-outcome-grid.svg)

The pie in every card is an **estimated work-contribution allocation**, not time tracking, legal ownership, or a productivity score: **35% human leadership and authority, 40% AI-assisted technical execution, and 25% CML/Fermata integrity method.** Human authorship, approval, and accountability remain mine.

The dashboard is intentionally limited to the three active pull requests currently being monitored.

| Pull request | Current public state | Evidence record | Source |
| --- | --- | --- | --- |
| Microsoft FHIR Server #5829 | `OPEN` · upstream CI hold | Global suppressions removed; published Release build records 0 warnings / 0 errors and focused tests. Visible workflow is `action_required`, so CI is not claimed green. | [PR #5829](https://github.com/microsoft/fhir-server/pull/5829) · [Issue #5679](https://github.com/microsoft/fhir-server/issues/5679) |
| OpenAI Go #932 | `OPEN` · upstream CI hold | Targeted regression, compile, `go vet`, and diff checks are recorded. Mock-endpoint suite was unavailable; upstream CI is `action_required`. | [PR #932](https://github.com/openai/openai-go/pull/932) · [Issue #631](https://github.com/openai/openai-go/issues/631) |
| OpenAI Go #933 | `OPEN` · upstream CI hold | Focused tests, `go vet`, compile, Castiron, and diff checks are recorded; a full-suite pass is not claimed. Upstream CI is `action_required`. | [PR #933](https://github.com/openai/openai-go/pull/933) |

## Daily journals

- [2026-09-18 — Initial public record](journals/2026-09-18.md)

## Status rules

- `IMPLEMENTED` — changed in a named artifact with direct evidence.
- `VERIFIED` — checked against a reproducible test or authoritative record.
- `OBSERVED` — directly visible on a public source but not independently reverified.
- `HOLD` — intentionally not submitted or not ready for a public claim.
- `UNKNOWN` — not established by available evidence.

An open PR is not a completed result. A passing local test is not upstream acceptance. A merged PR is not automatically a release or production verification.

---

**Human-led. AI-assisted. Evidence-bound.**
