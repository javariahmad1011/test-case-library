# Common Test Case Mistakes

## Vague Titles

Bad: `Check login`  
Better: `Locked user cannot authenticate with otherwise valid credentials`.

## Steps Without a Known Starting State

If role, account state, data ownership, or previous transaction state matters, put it in Preconditions. Hidden setup makes results non-reproducible.

## Expected Result Repeats the Step

“User clicks Save → record saves” is too weak. Specify validation, confirmation, persisted values, audit/downstream impact, and duplicate/partial-state prevention where relevant.

## UI-Only Authorization Testing

A hidden button is not proof of authorization. Test direct URL/API access from a lower-privilege identity.

## Every Case Is High Priority

Use risk. Critical/High should be defensible by business impact, security, data loss/corruption, legal/compliance exposure, or release-critical functionality.

## Overloaded Cases

One case that validates creation, edit, search, export, delete, email, and audit creates ambiguous failures. Split by risk and business outcome while keeping setup reusable.

## No Recovery or Edge Coverage

Real systems fail during retries, timeouts, stale sessions, duplicate clicks, concurrent edits, gateway callbacks, and network transitions. These are often more valuable than a fifth happy-path variation.

## Unsafe Test Data

Do not use production credentials, personal data, real payment details, or unauthorized security payloads. Use approved synthetic/sandbox data and controlled environments.
