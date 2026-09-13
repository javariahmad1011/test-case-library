# QA Checklist

Use this as a release/test-design review prompt rather than a substitute for product-specific test cases.

## Functional and Data

- Critical user journeys have positive, negative, and recovery coverage.
- Required fields, formats, boundaries, duplicate rules, and cross-field dependencies are tested.
- Create/update/delete actions are independently verified after refresh or re-query.
- Calculations and totals reconcile from source values.
- Historical data is preserved where business/audit rules require it.
- Duplicate submission, retry, and idempotency behavior are known.

## Permissions and Security

- Unauthenticated, unauthorized, and lower-privilege roles are tested against UI **and** direct API/URL paths.
- Horizontal access (another user's/customer's record) is tested.
- Sensitive values are not exposed in URLs, logs, browser storage, exports, or error messages.
- Session timeout, logout, revocation, and account-state changes remove access as expected.
- Input is treated as data and safely handled; security tests occur only in authorized environments.

## API / Integration

- Success and documented error status codes are validated.
- Mandatory/optional fields, data types, enums, nulls, malformed payloads, and unknown IDs are covered.
- Timeouts/retries do not create duplicate business actions.
- Downstream failures produce deterministic recoverable states.
- API response and persisted/audited state agree.

## UI / Accessibility / Compatibility

- Keyboard navigation, focus, labels, errors, and status announcements support task completion.
- Responsive breakpoints, long content, and supported browsers/devices are covered.
- Loading, empty, error, disabled, and read-only states are clear.
- Date/time/currency/number formatting follows locale/business rules.

## Regression and Release

- Smoke suite covers service availability and critical paths.
- Sanity suite targets changed functionality after fixes/deployments.
- Regression selection considers shared components and downstream integrations.
- Critical/High defects have evidence, reproducible steps, impact, and retest coverage.
