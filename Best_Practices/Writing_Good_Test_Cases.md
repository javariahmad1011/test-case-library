# Writing Good Test Cases

## Purpose

A professional test case is a reproducible specification of a risk check. Another tester should be able to execute it, understand why it exists, identify the expected business state, and collect enough evidence to distinguish a product defect from data or environment failure.

## Anatomy of a Strong Test Case

**ID and traceability.** Use a stable identifier and link the case to a requirement, story, risk, defect, or business rule when a traceability system exists.

**Title.** Describe the condition and expected business behavior, not merely the screen: “Reject transfer above available balance” is stronger than “Transfer negative test.”

**Preconditions.** State account role, data state, feature configuration, dependencies, and session/environment assumptions. Avoid hidden setup knowledge.

**Test data.** Use concrete, controlled values or a clearly defined data class. For boundaries, state N-1/N/N+1. For permissions, identify the caller and target ownership relationship.

**Steps.** Keep actions reproducible and ordered. Include independent verification where a workflow persists important data. Do not mix unrelated business assertions into one case.

**Expected result.** Make it observable and falsifiable. Include validation message/state, persistence behavior, authorization, downstream/audit impact, and “no duplicate/partial change” when relevant.

## Priority vs Severity

- **Priority** answers: how urgently should this case be run or a defect be fixed for the release?
- **Severity** answers: how damaging is the failure to business, security, data, or users?

A cosmetic defect can be high priority before a major launch; a rarely reached data-corruption defect can be critical severity even if its execution frequency is low.

## Avoid These Patterns

- “Verify page works” with no measurable outcome.
- Expected result that simply repeats the step.
- Hard dependencies on earlier cases without explicit setup.
- Combining five unrelated validations into one huge case.
- Marking every case High/Critical.
- Checking only UI confirmation for a financial or persistent-data operation.
- Using production credentials or personally identifiable information as test data.

## Review Checklist

Before adding a case to regression, ask: Does it cover a meaningful risk? Is the starting state reproducible? Can two testers reach the same conclusion? Is the expected result objective? Does it overlap another case without adding risk coverage? Would a future tester understand what evidence to collect?
