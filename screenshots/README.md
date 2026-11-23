# Screenshot evidence index

All screenshots were captured in a controlled Microsoft Entra ID P2 lab. Upload each image to this `screenshots/` directory using the exact filename below. **The links will become active only after the corresponding PNG files are uploaded.**

| # | Evidence | Filename |
|---|---|---|
| 01 | PIM overview and navigation | [01-entra-pim-overview.png](./01-entra-pim-overview.png) |
| 02 | Available Microsoft Entra roles | [02-entra-pim-roles-baseline.png](./02-entra-pim-roles-baseline.png) |
| 03 | Reports Reader eligible assignments baseline: none | [03-entra-pim-reports-reader-baseline.png](./03-entra-pim-reports-reader-baseline.png) |
| 04 | Reports Reader active assignments baseline: none | [04-entra-pim-reports-reader-active-baseline.png](./04-entra-pim-reports-reader-active-baseline.png) |
| 05 | Cloud-only Marcus Reed test user | [05-entra-pim-test-user-created.png](./05-entra-pim-test-user-created.png) |
| 06 | Active Microsoft Entra ID P2 license | [06-entra-pim-test-user-p2-license.png](./06-entra-pim-test-user-p2-license.png) |
| 07 | No usable authentication methods before registration | [07-entra-pim-test-user-mfa-baseline.png](./07-entra-pim-test-user-mfa-baseline.png) |
| 08 | Microsoft Authenticator registered as default method | [08-entra-pim-test-user-mfa-registered.png](./08-entra-pim-test-user-mfa-registered.png) |
| 09 | Original role settings: eight-hour limit, no activation MFA requirement | [09-entra-pim-reports-reader-role-settings-baseline.png](./09-entra-pim-reports-reader-role-settings-baseline.png) |
| 10 | Editor showing one-hour maximum, Azure MFA and justification | [10-entra-pim-activation-security-configuration.png](./10-entra-pim-activation-security-configuration.png) |
| 11 | Saved activation controls confirmed | [11-entra-pim-activation-security-settings-saved.png](./11-entra-pim-activation-security-settings-saved.png) |
| 12 | Marcus Reed eligible Reports Reader assignment | [12-entra-pim-reports-reader-eligible-assignment.png](./12-entra-pim-reports-reader-eligible-assignment.png) |
| 13 | Eligible assignment visible to Marcus before activation | [13-entra-pim-user-eligible-role-before-activation.png](./13-entra-pim-user-eligible-role-before-activation.png) |
| 14 | One-hour activation request and required reason field | [14-entra-pim-reports-reader-activation-request.png](./14-entra-pim-reports-reader-activation-request.png) |
| 15 | Reports Reader displayed as Activated | [15-entra-pim-reports-reader-activation-result.png](./15-entra-pim-reports-reader-activation-result.png) |
| 16 | Successful PIM activation audit with justification and expiration | [16-entra-pim-reports-reader-activation-audit.png](./16-entra-pim-reports-reader-activation-audit.png) |
| 17 | No results under Active assignments after activation ended | [17-entra-pim-reports-reader-deactivation-verification.png](./17-entra-pim-reports-reader-deactivation-verification.png) |

## Publication review

Before public upload, redact correlation IDs, object IDs, IP addresses, passwords, QR codes, tokens and any other unnecessary identifiers. Preserve the relevant role names, configuration states, timestamps and success results. Screenshot 16 contains a correlation ID that should be redacted.
