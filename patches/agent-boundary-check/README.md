# Agent Boundary Check — standalone timing-test fix

**September 19, 2026 · Sherrie Joseph · Human-led, AI-assisted contribution**

**Publication state: PATCH PUBLISHED HERE; NOT SUBMITTED UPSTREAM.** No upstream pull request, merge, release, or maintainer approval is claimed. This directory is a published contribution artifact, not another item added to the existing three-PR monitoring dashboard.

[Read the exact patch](timing-test.patch) · [Upstream repository](https://github.com/sylvesterkaczmarek/agent-boundary-check) · [Pinned original test](https://github.com/sylvesterkaczmarek/agent-boundary-check/blob/112ed6904f151f27cae635d77c43a36124df76aa/tests/test_adapters.py)

## Scope

Base revision: `112ed6904f151f27cae635d77c43a36124df76aa`.

Only `tests/test_adapters.py` changes: **4 insertions, 2 deletions**. Both standard-library-only Python helpers in `test_agent_run_stops_its_background_tools` now use `-I -S`. The one-second adapter timeout, readiness assertion, expected timeout/non-timeout assertions, sleeps, and late-write assertion remain unchanged. No production adapter, process-cleanup implementation, probe, host setting, or permission boundary changes.

Patch SHA-256: `80f1ead16e2e07ce46781ff87be9ab1ab1f811fcd75babe64402d8e10dcc7b51`.

## Why this change

The test's synthetic parent starts a synthetic child. Their interpreter initialization and the parent's exit must fit within the normal-exit case's one-second deadline. In the diagnostic environment, import tracing recorded approximately 0.42 seconds of site initialization per ordinary interpreter. The normal-exit case could therefore time out despite reaching the end of its script. Isolating the helpers removed the reproduced startup-hook sensitivity.

Python documents that [`-I` isolates interpreter paths and Python environment settings, while `-S` suppresses automatic site initialization](https://docs.python.org/3.13/using/cmdline.html). These options apply only to synthetic test helpers here, not to real agents. This does not promise tolerance of arbitrary machine starvation and is not a security or sandbox-escape claim.

## Validation evidence and limits

The retained local timing-diagnosis pack records the following results on Linux x86_64, Python 3.13.5, pytest 9.0.2:

| Check | Recorded result |
| --- | --- |
| Original cleanup cases in affected environment | 1 passed, 1 failed; normal-exit timeout reproduced |
| Fixed cleanup cases in the same environment | 2 passed |
| All collected original tests with timing-only patch | 196 passed |
| Additional direct repetitions of the exact fixed cleanup test | 10/10 passed |
| Negative controls with deliberately broken group cleanup | Both cases detected the surviving child's late write |
| Controlled synthetic startup-hook environment | Original: 1 passed, 1 failed; fixed: 2 passed |

These are overlapping validations of one change, not separate repair counts. The diagnostic pack is retained locally; this page is a contributor-reported summary of that evidence, not upstream CI output.

During publication preparation, all **142 entries** in the retained timing pack's checksum manifest were verified. The original test file matched upstream blob `74647cc6a16076f386059be786a94be7b407c292`, and the uploaded patch matched the retained patch bytes. A fresh targeted run with the original test fixture enabled produced:

```text
python -m pytest -q tests/test_adapters.py::test_agent_run_stops_its_background_tools
2 passed in 5.36s
Exit code: 0
```

That publication recheck used the timing-only reconstructed snapshot, a synthetic HOME, `PYTHONPATH=src`, and `PYTEST_DISABLE_PLUGIN_AUTOLOAD=1`. It did not rerun the entire suite.

**Remaining validation:** the local source tree was reconstructed from hash-checked upstream files rather than a normal complete clone. All runtime and test modules were present, but omitted repository files were not covered by the broad source-scanning test. Full-checkout confirmation, the other Python/operating-system combinations, complete distribution checks, and upstream CI remain unestablished. The previously recorded 211-test result included a separate local candidate and is deliberately not used as this standalone patch's suite count. No other local candidate is included or disclosed by this patch.

## Apply and validate

On a complete checkout of the pinned revision, with this patch saved outside the checkout:

```bash
git apply --check ../timing-test.patch
git apply ../timing-test.patch
python -m pytest -q tests/test_adapters.py::test_agent_run_stops_its_background_tools
python -m pytest -q
git diff --check
```

Run the remaining platform and package checks specified in the [pinned CI workflow](https://github.com/sylvesterkaczmarek/agent-boundary-check/blob/112ed6904f151f27cae635d77c43a36124df76aa/.github/workflows/ci.yml). These commands are a reproduction recipe, not a claim that all CI jobs have executed.

## Upstream submission handoff

**STATE → HANDOFF → OWNERSHIP → VALIDATION → NEXT ACTOR → HUMAN AUTHORITY**

- **State:** the standalone timing patch is published in this Work Record. The upstream main branch was rechecked at the same base revision; its open-PR collection returned no entries during publication preparation.
- **Blocker:** the connected account has read-only access upstream, no accessible `cstolting-collab/agent-boundary-check` fork was found, and the available connector exposes no fork-creation action. An upstream PR was not created; no PR number is invented.
- **Next actor:** Sherrie creates a normal GitHub fork under `cstolting-collab`, retaining the name `agent-boundary-check`. No upstream write permission is needed for the fork-based contribution route. After the fork is accessible for writing, the contributor role can create a dedicated branch, apply this exact one-file patch, and open the authorized PR after rechecking its base and diff.
- **Intended PR title:** `test: isolate cleanup helpers from Python startup hooks`.
- **Completion conditions:** exact patch/diff verified on the submission branch, remaining relevant CI evidence inspected, and upstream review/merge state verified independently. Publishing this artifact does not meet those upstream gates.
- **Authority:** Sherrie requested publication of this timing fix. No merge, release, extra source change, unrelated finding disclosure, or monitoring expansion is authorized or claimed by this entry.

Upstream code is by Sylvester Kaczmarek. Its [MIT license](LICENSE) is preserved. This change was prepared with AI assistance at Sherrie Joseph's direction; CML/Fermata is the continuity and evidence workflow, not a separate author or an executing autonomous runtime.

**Progress is worth recording before completion. Completion is worth claiming only when verified.**
