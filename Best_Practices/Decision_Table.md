# Decision Table Testing

Decision tables are effective when the outcome depends on multiple conditions and simple one-condition test cases can miss interactions.

## Example: Fund Transfer

| Sufficient Balance | Within Transaction Limit | Within Daily Limit | Beneficiary Active | OTP Valid | Expected Outcome |
|---|---|---|---|---|---|
| Yes | Yes | Yes | Yes | Yes | Transfer succeeds |
| No | Yes | Yes | Yes | Yes | Reject: insufficient funds |
| Yes | No | Yes | Yes | Yes | Reject: transaction limit |
| Yes | Yes | No | Yes | Yes | Reject: daily limit |
| Yes | Yes | Yes | No | Yes | Reject: beneficiary not eligible |
| Yes | Yes | Yes | Yes | No | Reject: authentication failure |

## Professional Practice

Prioritize combinations that produce distinct business outcomes. Confirm precedence if multiple rules fail at once: which error should the user see, and which control should be evaluated first? For security-sensitive rules, also verify the server does not disclose unnecessary information while deciding the outcome.
