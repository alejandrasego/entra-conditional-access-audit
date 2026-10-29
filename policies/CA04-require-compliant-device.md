# CA04: Require a compliant device for Microsoft 365 apps

**Status:** Designed
**Mode for testing:** Report-only

## Purpose
Allow access to company data only from devices that meet baseline security requirements (such as encryption, screen lock, and supported OS version), as reported by Intune.

## Assignments
- **Users included:** All users
- **Users excluded:** Emergency (break-glass) accounts group
- **Target resources:** Office 365 (Exchange Online, SharePoint Online, Teams)
- **Conditions:** Device platforms: Windows, macOS, iOS, Android

## Access controls
- **Grant:** Require device to be marked as compliant
- **Session controls:** None

## Control mapping
- NIST SP 800-53 Rev. 5: AC-19 access control for mobile devices; CM-6 configuration settings
- NIST SP 800-63B: Not applicable (device posture, not authenticator)
- CIS Controls v8: Safeguard 4.1 (secure configuration process)

## Rationale
A correct password and MFA do not show that the device is safe. A compliance check adds that signal.

## Known risks and edge cases to test
- Personal or unenrolled device
- New device that is not yet enrolled (enrollment may be blocked by the policy itself, a common circular problem; document how enrollment is exempted)
- Device that was compliant and then falls out of compliance
- Compliance state lag after a device changes

## Test profiles that exercise this policy
1, 2, 10

## Results
See docs/03-test-results.md.
