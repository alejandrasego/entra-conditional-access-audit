# CA05: Block high-risk sign-ins

**Status:** Designed
**Mode for testing:** Report-only
**License note:** Risk-based conditions depend on Microsoft Entra ID P2 (Identity Protection). Confirm current licensing before testing.

## Purpose
Block sign-ins that Microsoft's risk detection rates as high risk, such as impossible travel or anonymous IP addresses.

## Assignments
- **Users included:** All users
- **Users excluded:** Emergency (break-glass) accounts group
- **Target resources:** All cloud apps
- **Conditions:** Sign-in risk: High

## Access controls
- **Grant:** Block access
- **Session controls:** None

## Control mapping
- NIST SP 800-53 Rev. 5: AC-2(12) account monitoring for atypical usage; SI-4 system monitoring
- NIST SP 800-63B: Not applicable
- CIS Controls v8: To be confirmed

## Rationale
Adds a decision based on the behavior of a sign-in, which static rules cannot capture.

## Known risks and edge cases to test
- False positives that lock out a legitimate user: what is the recovery process?
- Risk signals are hard to simulate in a lab; document exactly how the test was simulated and what it does not prove
- Interaction with CA01 when both apply

## Test profiles that exercise this policy
8

## Results
See docs/03-test-results.md.
