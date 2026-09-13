# API Testing Test Cases

## Overview

The API suite validates observable behavior at the service boundary: status codes, authentication vs authorization, schema/contract behavior, payload validation, idempotency, concurrency, referential restrictions, and agreement between API responses and persisted state.

## Test Assets

| Workbook | Cases | Primary Coverage |
|---|---:|---|
| `GET_API.xlsx` | 7 | Retrieval, 404, 401/403, query/pagination, headers and response time |
| `POST_API.xlsx` | 7 | Creation, schema validation, duplicate key, auth, idempotency, persistence |
| `PUT_API.xlsx` | 7 | Update, replacement semantics, ETag/concurrency, protected fields, schema |
| `DELETE_API.xlsx` | 7 | Delete, idempotency, 401/403, references/conflicts, retention |

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
