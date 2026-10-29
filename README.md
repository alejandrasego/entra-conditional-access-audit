# Entra ID Conditional Access Audit

A simulated policy documentation set and test record for Microsoft Entra ID Conditional Access, covering MFA enforcement, device compliance rules, and risk-based sign-in blocks. Policies are tested against 10 fictional sign-in profiles, and the edge cases where access fails are documented along with the fixes.

All users, devices, and sign-ins in this repository are fictional. Nothing here has been deployed to a production tenant.

**Author:** Alejandra Segoviano | **Focus:** Identity & Access Management
**Platform:** Microsoft Entra ID (Conditional Access) | **Frameworks referenced:** NIST SP 800-53, NIST SP 800-63B, CIS Controls v8

## Project status

| Phase | Status |
|---|---|
| 1. Design and documentation (6 policies, 10 sign-in profiles, expected results) | In progress |
| 2. Testing in a lab tenant (What If tool and report-only mode) | Not started |
| 3. Edge-case analysis and one documented policy revision | Not started |

This README will be updated as each phase is completed.

## Policies in scope

| ID | Policy | Control type |
|---|---|---|
| CA01 | Require MFA for all users | Grant: require MFA |
| CA02 | Require MFA for administrator roles | Grant: require MFA |
| CA03 | Block legacy authentication | Block |
| CA04 | Require a compliant device for Microsoft 365 apps | Grant: require compliant device |
| CA05 | Block high-risk sign-ins | Block (risk-based) |
| CA06 | Block sign-ins from unapproved countries | Block (location-based) |

## How testing will work

- Policies are created in **report-only mode** so they cannot lock anyone out.
- Each of the 10 sign-in profiles is run through the **What If tool**, and the results are compared with the expected result written in advance.
- Differences between expected and actual results are recorded as failure cases, and at least one policy revision is documented with before-and-after results.

## Repository contents

```
README.md
policies/        one document per policy, plus a blank template
docs/
  01-scope-and-assumptions.md
  02-test-profiles.md
  03-test-results.md
  04-policy-change-log.md
  05-edge-cases.md
```

## Limitations

- This is a lab exercise. It does not reflect the full complexity of a production tenant, such as legacy applications, third-party integrations, or real user behavior.
- The What If tool shows which policies would apply and what they would require. It does not exercise a real interactive sign-in.
- Risk-based policies depend on Entra ID P2 licensing and Identity Protection signals, which are simulated in a lab.
- Control mappings to NIST and CIS are the author's own and should be read as a reference, not an audit opinion.
