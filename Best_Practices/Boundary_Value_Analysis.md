# Boundary Value Analysis

Boundary Value Analysis (BVA) targets values where defects frequently occur: just below, exactly at, and just above a rule boundary.

## Typical QA Boundaries

- Password length: `min-1`, `min`, `min+1`, `max-1`, `max`, `max+1`
- Transfer amount: `0`, smallest allowed amount, available balance, transaction limit, daily cumulative limit
- Cart quantity: `0`, `1`, available stock, stock+1, maximum order quantity
- Dates: day before/start/end/day after eligibility or reporting periods
- Session timeout: immediately before, exactly at, and after expiration threshold
- Search/export size: last record on page N and first record on page N+1

## Professional Use

Do not create every theoretical boundary if it adds no risk value. Identify which component owns the rule and verify both acceptance at valid boundaries and rejection outside them. If client and API validation differ, record that as a defect/risk because server-side enforcement is authoritative.

## Example

If a transfer limit is 5,000.00, meaningful cases include 4,999.99, 5,000.00, and 5,000.01, plus the interaction with available balance and daily cumulative limits. A decision table may be more effective when several limits overlap.
