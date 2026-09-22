# Real-Workload Performance Evidence Standard

Use this standard whenever a contribution claims performance, efficiency, latency, throughput, resource, transport, caching, retry, concurrency, or storage improvement, or when a maintainer has asked whether an optimization is materially useful.

## Required evidence

1. **Use a supported workload.** Measure a path that real users or shipped examples exercise. A microbenchmark may supplement this evidence but must not substitute for it when material workload benefit is the acceptance question.
2. **Verify correctness before timing.** Baseline and treatment must produce equivalent expected results for the measured workload before performance numbers are accepted.
3. **Hold the environment constant.** Record the exact revision, dependency/provider versions, runtime version, workload size, operation count, and relevant service/container configuration.
4. **Compare baseline and treatment directly.** Use the current or immediately previous supported behavior as the baseline. Do not compare against an invented or weakened control.
5. **Separate startup from steady-state work.** If startup is not part of the claim, report it separately and exclude it from the timed operation. If startup is part of the claim, measure and label it explicitly.
6. **Use repeated alternating observations.** Alternate baseline/treatment order where practical to reduce drift from service load, caches, network conditions, or host state. Report the observation count.
7. **Report distribution, not one favorable number.** At minimum publish median plus a spread measure such as p95, min/max, or confidence interval. Include the absolute and relative delta.
8. **Preserve failure and compatibility boundaries.** A faster path is not accepted as equivalent if it changes error categories, permissions, data integrity, cancellation, retry safety, size limits, or documented semantics without an explicit decision.
9. **Do not promote unrun evidence.** A benchmark harness that has not executed against the required live provider is `BENCHMARK READY`, not `VERIFIED`.
10. **Tie the result to the submission decision.** Record whether the workload evidence supports, weakens, or leaves unresolved the performance rationale. Do not call a technically passing patch complete when its material-benefit question remains unanswered.

## Evidence record

A complete performance record should contain:

- workload description and why it represents a supported user path;
- exact baseline and treatment revisions;
- provider/dependency/runtime versions;
- operation count, payload/file sizes, warmup policy, and observation count;
- correctness-parity result;
- raw or machine-readable samples when practical;
- median and distribution summary;
- startup treatment;
- known limitations and unavailable environments;
- direct links to the benchmark code and run evidence.

## Status language

- **BENCHMARK READY** — harness is implemented and statically/CI validated, but required live workload execution has not occurred.
- **MEASURED** — the workload executed and raw measurements were captured.
- **VERIFIED PERFORMANCE EVIDENCE** — correctness parity, environment identity, repeated measurements, and result record are all present.
- **UNKNOWN / HOLD** — required workload or environment cannot currently be exercised.

Passing CI proves the benchmark code is valid enough to run. It does not prove the performance claim itself.
