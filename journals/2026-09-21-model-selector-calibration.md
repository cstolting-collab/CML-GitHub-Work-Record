# Model Selector Calibration — Public Research Note

**Date:** 2026-09-21  
**Evidence status:** OBSERVED  
**Scope:** bounded local model-selection experiment  
**Build disclosure:** intentionally limited

## What happened

A local selector calibration produced an inconsistency that was preserved instead of being silently corrected.

The calibration used four fixed synthetic cases:

- one case where every required condition held and a positive evaluation action was expected;
- three control cases where one required condition did not hold and no action was expected.

The three control cases behaved as expected. The positive case did not: the local model returned the same no-action response it returned for the controls.

The calibration stopped, saved the observation, raised a visible warning, and made **no CML source change**.

## What we tested next

The follow-up tests isolated the behavior without changing the build.

| Test | Observed result |
| --- | --- |
| Direct evidence → action selection | Incorrect no-action result |
| Ask only whether all required conditions hold | Correct: all conditions hold |
| Make the validated intermediate state explicit, then select the action | Correct positive action |

The enum/output ordering was also reversed in a control test. The outcome remained no-action, so simple enum ordering did not explain the original failure.

## Current interpretation

The evidence does **not** show that the model repaired itself, that continuity alone caused the change, or that general reasoning reliability improved.

What it does show in this bounded test is narrower:

> **Explicit state materialization changed the selector outcome from incorrect to correct.**

The model could correctly evaluate the underlying condition. The failure appeared at the transition from implicitly evaluated evidence directly to an action. When the intermediate state was made explicit and validated, the expected action followed.

A useful research framing is:

**EVIDENCE → STATE → VALIDATION → ACTION**

rather than asking the model to jump directly from raw evidence to action.

This is an observed result, not a general claim.

## Why this matters to the continuity work

The broader continuity question is not whether a model can produce more output. It is whether the system can preserve enough explicit state for the next decision to be made reliably without forcing the human to reconstruct what happened.

This experiment is interesting because the underlying condition was understood in isolation, while the direct handoff from evidence to action failed. Making the intermediate state explicit changed that bounded outcome.

That is consistent with the research direction, but it is **not yet proof that continuity is the cause**.

## What remains private

This public note intentionally does **not** publish:

- internal build structure;
- implementation files or local service layout;
- exact calibration prompts;
- private automation wiring;
- internal source paths;
- unpublished CML implementation details.

The purpose of this note is to share the observed behavior and research direction without publishing the build itself.

## Next validation

The next controlled step is a matched A/B experiment:

**A — direct selector:** evidence → action  
**B — explicit-state selector:** evidence → validated state → action

The same model, fixed vectors, deterministic settings and preserved receipts should be used across repeated trials.

The failed baseline should remain preserved. Policy or source should not be changed merely to make the calibration pass.

A stronger result would require repetition showing that the explicit-state path consistently succeeds where the direct path fails.

## Limits

This experiment concerns one bounded selector task using a local model. It does not establish general model reliability, renderer behavior, production correctness, causation by continuity, or self-repair.

No claim is made that CML changed the model, changed model weights, or autonomously repaired the system.

---

**Human-led. AI-assisted. Evidence-bound.**

This record is shared so others can follow the research direction, test similar ideas independently, and build on the observation without treating an early result as a conclusion.
