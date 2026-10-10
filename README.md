# CML GitHub Work Record

**Problem:** Human-led, AI-assisted repair work across many forks is impossible to audit. You lose what was tried, what failed, what is blocked.

**What this is:** Public, evidence-bound record of engineering work, validation standards, experiments, failures, and handoffs. Reporting destination, not a repair target.

**Historical State — Readback: 2026-09-29**
The following is a dated snapshot, not a fresh verification of upstream status.

**AI continuity entry point:** [AI_SOURCE.md](AI_SOURCE.md) · [Daily rules](standards/DAILY-GITHUB-RULES.md) · [Master agent prompt](prompts/MASTER-AI-AGENT-PROMPT.md)

| Item | Head | Operational state | Next actor |
| :--- | :--- | :--- | :--- |
| OpenAI Codex #47555 — Windows sandbox setup stuck | `dccef51` | IMPLEMENTED ON FORK / UPSTREAM HANDOFF — fix committed, Windows regression coverage added. Upstream PR creation restricted to collaborators. | Codex maintainer — review/cherry-pick |
| Codex Security #973 — fork candidate #1 | `e7f2731` | HOLD — FORK CANDIDATE VALIDATED. Exact-head node-ci: 46 jobs: 43 success, 3 skipped, 0 failed, 0 pending. Draft, no upstream PR submitted. Prereq #810 still open. | Upstream #810 maintainers |
| OpenAI Agents Python #5088 — native Modal read | `f6e6368` / `a67a69d` | HOLD — Benchmark READY -> MEASURED. 18/18 fork validation passed. Median: shell 3.4937s vs native 2.7945s (-20.0% code-path delta) with correctness parity. | Maintainer review |
| FHIR Server #5829 | `512dad5` | BLOCKED — maintainer-triggered Azure pipeline failed, Check Metadata failed 2026-09-21 | Upstream maintainer |

**30 sec try:**
```bash
git clone https://github.com/cstolting-collab/cml-github-work-record
cd cml-github-work-record
cat standards/DAILY-GITHUB-RULES.md
cat journals/2026-09-23.md # exact links to fix branches and CI runs
```

**Method:** STATE → HANDOFF → OWNERSHIP → VALIDATION → NEXT ACTOR → HUMAN AUTHORITY. Rule: Read · Verify · Prepare · Hold.

2026-09-29 external contribution audit: 12 upstream PRs located outside this account: 8 open, 3 closed after equivalent/original fixes merged upstream, 1 closed unmerged.

**Public boundary:** Private workflow mechanics, credentials, unpublished patches not published. Open PR != completed result.

License: [Apache-2.0](LICENSE) · Topics: cml, work-log, evidence, reproducibility
