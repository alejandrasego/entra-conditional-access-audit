# CA01: Require MFA for all users

**Status:** Designed
**Mode for testing:** Report-only

## Purpose
Reduce account takeover from stolen or guessed passwords by requiring a second factor for every sign-in to every cloud app.

## Assignments
- **Users included:** All users
- **Users excluded:** Emergency (break-glass) accounts group. Excluded so the tenant cannot be locked out if MFA or the policy engine fails. These accounts are monitored separately (see docs/01-scope-and-assumptions.md).
- **Target resources:** All cloud apps
- **Conditions:** None (applies to all sign-ins)

## Access controls
- **Grant:** Require multifactor authentication
- **Session controls:** None

## Control mapping
- NIST SP 800-53 Rev. 5: IA-2(2) multi-factor authentication for non-privileged accounts
- NIST SP 800-63B: Authenticator Assurance Level 2 (multi-factor)
- CIS Controls v8: Safeguards 6.3 and 6.4 (MFA for externally exposed apps and remote access)

## Rationale
Passwords alone are the most common way accounts are compromised. One baseline policy covers every user and app, and the other policies add stricter rules on top of it.

## Known risks and edge cases to test
- New hire who has not yet registered an MFA method
- Guest and contractor accounts (are they in scope?)
- Service accounts and shared mailboxes that cannot complete an MFA prompt
- Break-glass exclusion: confirm it works and is monitored

## Test profiles that exercise this policy
1, 3, 5, 6, 7, 9

## Results
See docs/03-test-results.md.
