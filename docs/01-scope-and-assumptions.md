# Scope and assumptions

## In scope
Six Conditional Access policies (CA01 to CA06), ten fictional sign-in profiles, expected results written before testing, and a record of where the policies fail or conflict.

## Out of scope
Production tenants, real user data, third-party identity providers, and anything outside Conditional Access, such as Privileged Identity Management or access reviews.

## Assumptions
- **Environment:** A lab Entra tenant with fictional users. Real client or employer data is never used.
- **Licensing:** Conditional Access requires Entra ID P1 or P2 (or an equivalent bundle). Risk-based policies need P2. Confirm the licensing used for testing and record it here once the lab is set up.
- **Security Defaults:** Disabled in the lab tenant, because Security Defaults and Conditional Access cannot be used together.
- **Break-glass accounts:** Two emergency admin accounts are excluded from every policy so the tenant cannot be locked out. They use long, unique credentials, are stored offline, and every sign-in to them should trigger an alert. Their exclusion is documented in each policy.
- **Testing method:** Report-only mode and the What If tool. No policy is switched to "On" in a way that could lock out the admin running the tests.
- **Simulated signals:** Sign-in risk and device compliance are simulated. Document exactly how each was simulated and what that does and does not prove.

## Remaining risk (to complete after testing)
List the risks that remain after the policies are applied, such as stolen session tokens, MFA fatigue attacks, and compromised compliant devices, along with the threshold at which the risk is considered acceptable. 
