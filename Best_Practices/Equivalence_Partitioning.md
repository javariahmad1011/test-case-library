# Equivalence Partitioning

Equivalence Partitioning groups inputs or states that should be treated the same by the system, allowing representative tests without testing every possible value.

## Example Partitions

For an email field: valid corporate email, valid internationalized/allowed format, malformed local part, missing domain, prohibited domain, duplicate existing email, blank value.

For a user-management action: authorized admin, authorized limited manager, standard user, disabled user, unauthenticated caller.

For an API identifier: existing owned resource, existing unowned resource, deleted resource, unknown well-formed ID, malformed ID.

## How to Apply It

1. Identify the rule that divides behavior.
2. Define valid and invalid classes.
3. Choose representative values for each class.
4. Add boundaries where the partition is numeric, date-based, or length-based.
5. Add combinations only where interaction changes the expected outcome.

Equivalence Partitioning should reduce redundant execution, not hide important risk. High-risk partitions such as unauthorized access or financial thresholds deserve explicit cases even if they appear similar to other invalid inputs.
