# Test profiles

Ten fictional sign-in profiles. The "Expected result" column is written before testing. The "Actual result" column is filled in during Phase 2.

| # | Fictional profile | Scenario | Policies in play | Expected result (design) | Actual result |
|---|---|---|---|---|---|
| 1 | Maria, Finance | Managed laptop, office network | CA01, CA04 | Allowed after MFA | |
| 2 | Daniel, Sales | Personal, unenrolled phone | CA01, CA04 | Blocked from Microsoft 365 apps (device not compliant) | |
| 3 | Priya, IT admin | Signing in from home | CA01, CA02, CA04 | MFA required; allowed on a compliant device | |
| 4 | Luis, Operations | Traveling abroad | CA06 | Blocked unless a temporary exception applies | |
| 5 | Ana, new hire | No MFA method registered yet | CA01, CA04 | Prompted to register MFA; check that registration is not blocked by CA04 | |
| 6 | Shared mailbox or scanner account | Uses a legacy protocol | CA03 | Blocked | |
| 7 | Sam, contractor (guest) | External user signing in | CA01 | Depends on whether guests are in scope; document the decision | |
| 8 | Jordan, regular user | Sign-in flagged high risk | CA05 | Blocked | |
| 9 | Break-glass account | Emergency admin sign-in | Excluded from all | Allowed without MFA; alert raised | |
| 10 | Chris, regular user | Unenrolled laptop | CA04 | Blocked from Microsoft 365 apps | |

Notes:
- Profile 5 is a common circular problem: a device or location rule can stop a new user from reaching the page where they register MFA.
- Profile 7 depends on a design decision. Whichever way it goes, record it and the reasoning.
