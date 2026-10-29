# CA06: Block sign-ins from unapproved countries

**Status:** Designed
**Mode for testing:** Report-only

## Purpose
Reduce exposure to sign-in attempts from regions where the organization has no users.

## Assignments
- **Users included:** All users
- **Users excluded:** Emergency (break-glass) accounts group; a documented temporary-travel exception group
- **Target resources:** All cloud apps
- **Conditions:** Locations: include any location, exclude the named location "Approved countries"

## Access controls
- **Grant:** Block access
- **Session controls:** None

## Control mapping
- NIST SP 800-53 Rev. 5: AC-17 remote access
- NIST SP 800-63B: Not applicable
- CIS Controls v8: To be confirmed

## Rationale
A simple, low-cost rule that removes a large part of untargeted attack traffic.

## Known risks and edge cases to test
- Employee traveling abroad (profile 4): how is a legitimate exception granted and removed?
- VPN exit locations and mobile carrier IP addresses that map to the wrong country
- IP geolocation is approximate, so this control reduces risk but is not exact

## Test profiles that exercise this policy
4

## Results
See docs/03-test-results.md.
