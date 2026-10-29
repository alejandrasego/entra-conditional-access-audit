# CA03: Block legacy authentication

**Status:** Designed
**Mode for testing:** Report-only

## Purpose
Close the gap where older protocols (such as basic authentication) cannot perform MFA and would let a sign-in bypass CA01 and CA02.

## Assignments
- **Users included:** All users
- **Users excluded:** Emergency (break-glass) accounts group
- **Target resources:** All cloud apps
- **Conditions:** Client apps: Exchange ActiveSync clients and other legacy clients

## Access controls
- **Grant:** Block access
- **Session controls:** None

## Control mapping
- NIST SP 800-53 Rev. 5: IA-2 identification and authentication; CM-7 least functionality
- NIST SP 800-63B: Authenticator requirements (legacy protocols cannot meet AAL2)
- CIS Controls v8: Safeguards 6.3 and 6.4

## Rationale
An MFA policy is only as strong as the weakest sign-in path. Blocking protocols that cannot prompt for MFA removes that path.

## Known risks and edge cases to test
- Shared mailbox, scanner, printer, or service account that relies on legacy protocols
- Older mail clients still in use
- Use report-only first and review the sign-in logs for "other clients" before enforcing

## Test profiles that exercise this policy
6

## Results
See docs/03-test-results.md.
