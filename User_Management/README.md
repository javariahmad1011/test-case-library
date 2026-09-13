# User Management Test Cases

## Overview

This folder models administration of application identities after authentication. The focus is role-based access control, unique identity fields, user lifecycle state, auditability, destructive actions, search/filter integrity, and server-side authorization.

## Test Assets

| Workbook | Cases | Primary Coverage |
|---|---:|---|
| `User_Creation.xlsx` | 12 | Creation, roles, uniqueness, invitation, inactive state, audit |
| `User_Search.xlsx` | 12 | Search/filter, pagination, special input, permissions, performance |
| `User_Edit.xlsx` | 12 | Role/state edits, concurrency, authorization, audit, persistence |
| `User_Delete.xlsx` | 12 | Delete/archive policy, referential restrictions, RBAC, idempotency, retention |

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
