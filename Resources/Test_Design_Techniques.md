# Test Design Techniques Reference

| Technique | Best Used For | Example |
|---|---|---|
| Positive Testing | Core business flow | Valid customer checkout |
| Negative Testing | Rejection and recovery | Incorrect password, malformed payload |
| Boundary Value Analysis | Limits and thresholds | Quantity N-1/N/N+1 |
| Equivalence Partitioning | Representative input/state classes | Valid vs invalid role/account classes |
| Decision Table | Rule combinations | Balance × limit × OTP × beneficiary state |
| State Transition | Entity lifecycle | Pending → Active → Locked → Reactivated |
| Pairwise / Combinatorial | Configuration combinations | Browser × role × payment method |
| Error Guessing | Experience-based risk | Double click, stale tab, refresh during submit |
| Exploratory Testing | Unknown/complex behavior | Payment gateway failure recovery |
| Risk-Based Testing | Prioritization | Money movement and authorization before cosmetics |
| Accessibility Testing | Inclusive operability | Keyboard + screen reader completion |
| Compatibility Testing | Platform differences | Safari/iOS vs Chrome/Android |
| Performance Testing | Capacity and responsiveness | p95 under concurrent load |
| Security-minded QA | Access/control validation | ID tampering, session revocation, enumeration |

## Combining Techniques

Strong test design usually combines techniques. A transfer limit is not only a boundary problem: it interacts with available balance, daily limit, beneficiary state, OTP, authorization, retries, and ledger consistency. Use the smallest set of cases that still distinguishes each meaningful business outcome and risk.
