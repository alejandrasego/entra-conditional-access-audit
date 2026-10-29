# Edge cases and failure cases

Start from these candidates, then keep only what testing actually shows and add anything new you find.

## Candidates to check
1. **Registration deadlock:** A new user cannot register MFA because the device-compliance policy blocks the registration page.
2. **Guest users:** CA01 applies, but guests cannot satisfy the device rule.
3. **Service accounts and shared mailboxes:** MFA cannot be completed, and legacy blocking breaks them.
4. **Break-glass accounts:** Excluded from every policy, so they need monitoring and alerts.
5. **Policy overlap:** Two policies both apply, and the strictest one wins; document which.
6. **Traveling employee:** Country block stops a legitimate user, and the exception process has to be quick but controlled.
7. **VPN or carrier IP in the wrong country:** A geolocation mismatch causes a false block.
8. **Compliance lag:** A device that just became compliant (or non-compliant) is still treated by its old state for a time.
9. **False-positive risk block:** A legitimate user is blocked and needs a recovery path.
10. **Report-only does not prove everything:** Some grant controls need real interaction and cannot be fully evaluated in report-only mode.

## Confirmed failure cases (from testing)
| Case | What happened | Fix or accepted risk |
|---|---|---|
| | | |
