# State Transition Testing

State Transition Testing validates how the system behaves when an entity moves between defined states, including whether invalid transitions are prevented.

## Common QA State Models

**User account:** Pending Verification → Active → Locked/Disabled → Reactivated/Deleted.

**Password reset token:** Issued → Used or Expired/Revoked. A Used or Expired token must not transition back to valid.

**Order/payment:** Cart → Pending Payment → Paid → Fulfilled → Refunded/Cancelled, with explicit rules for failed or timed-out payments.

**Session:** Anonymous → Authenticated → Privilege Changed/Rotated → Idle Expired/Logged Out/Revoked.

## What to Test

- Every valid transition that represents a business path.
- Invalid transitions such as “Refunded → Paid” without a new transaction.
- Repeated events/idempotency, for example clicking Submit twice.
- Transition boundaries such as token expiry or session timeout.
- Persistence after refresh, re-login, service retry, or asynchronous callback.
- Audit history so the previous state is not silently lost.

State-transition tests are especially valuable for defects that appear only after retries, timeouts, concurrent actions, or partial integration failures.
