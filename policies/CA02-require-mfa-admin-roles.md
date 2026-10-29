# CA02: Require MFA for administrator roles

**Status:** Designed
**Mode for testing:** Report-only

## Purpose
Apply stricter authentication to the accounts that can change tenant configuration, since a compromised admin account has the highest impact.

## Assignments
- **Users included:** Directory roles: Global Administrator, Privileged Role Administrator, Security Administrator, Conditional Access Administrator, User Administrator, Exchange Administrator (extend as needed)
- **Users excluded:** Emergency (break-glass) accounts group
- **Target resources:** All cloud apps
- **Conditions:** None

## Access controls
- **Grant:** Require multifactor authentication. Optional hardening to document and compare: require a phishing-resistant authentication strength.
- **Session controls:** Sign-in frequency to be decided and documented

## Control mapping
- NIST SP 800-53 Rev. 5: IA-2(1) multi-factor authentication for privileged accounts; AC-6 least privilege
- NIST SP 800-63B: Authenticator Assurance Level 2 or higher
- CIS Controls v8: Safeguard 6.5 (MFA for administrative access)

## Rationale
Admin accounts are the highest-value target. This policy overlaps with CA01 on purpose, so a mistake in one does not remove protection from admins.

## Known risks and edge cases to test
- Admin on a personal device or unmanaged network
- Admin role assigned temporarily (is the policy still applied?)
- Break-glass exclusion

## Test profiles that exercise this policy
3, 9

## Results
See docs/03-test-results.md.
