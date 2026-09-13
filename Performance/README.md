# Performance Test Scenarios

## Overview

The performance suite describes measurable scenarios rather than arbitrary “fast/slow” checks. Cases use workload, percentile, throughput, error-rate, resource, correctness, and recovery language that can be implemented with JMeter, k6, Gatling, or a similar tool.

## Test Assets

| Workbook | Cases | Primary Coverage |
|---|---:|---|
| `Search.xlsx` | 7 | Baseline, concurrency, spike, complex filters, soak, correctness |
| `Dashboard.xlsx` | 7 | Time-to-data, concurrency, request fan-out, large datasets, soak |
| `Login_Load.xlsx` | 7 | Authentication baseline, concurrency/spike, rate limiting, soak, recovery |

## Coverage Strategy

The suite combines positive business paths with negative validation, boundary analysis, permissions/security, UI behavior, accessibility/compatibility where relevant, regression risk, and operational edge cases such as retries, stale state, duplicate submission, or network interruption. High-risk behaviors are validated at the authoritative layer whenever possible rather than trusting a disabled/hidden UI control.

## Test Design Techniques

- Boundary Value Analysis for limits, lengths, dates, quantities, and timeout thresholds.
- Equivalence Partitioning for valid and invalid data/identity/state classes.
- Decision-based coverage for combinations of role, state, action, and outcome.
- State Transition Testing for lifecycle behavior and invalid transitions.
- Risk-based prioritization for access, money/data loss, destructive actions, and downstream integrity.
- Cross-layer verification through UI, API, audit, and database checks when available.

## Execution Standard

1. Confirm prerequisites and use isolated QA data.
2. Execute the numbered steps without silently correcting the test condition.
3. Compare observed behavior with the Expected Result, including persistence and downstream effects.
4. Record Actual Result, Status, tester, date, and evidence/defect reference.
5. For Critical/High failures, verify the blast radius and include related cases in targeted regression.

## Quality Expectations

A passing case requires more than seeing a success message. The persisted business state must be correct, protected data must remain protected, duplicate or partial operations must not occur, and the result should remain correct after refresh/re-query/re-authentication where applicable.

## Notes for Interview Review

The cases are intentionally detailed so they can support discussion of **why** a scenario matters, what risk it addresses, how data would be prepared, what evidence would be collected, and what additional regression would be selected if the case failed.
