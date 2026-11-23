# Microsoft Entra Privileged Identity Management (PIM) — Just-in-Time Access

**IAM Portfolio Project 5** | Microsoft Entra ID P2 | Identity & Access Management | Privileged Access Security

## Executive summary

This hands-on lab demonstrates a controlled privileged-access lifecycle using Microsoft Entra Privileged Identity Management (PIM). A dedicated cloud-only test identity, **Marcus Reed**, was granted **eligible** (not permanently active) access to the low-impact **Reports Reader** role. PIM activation controls were strengthened, a one-hour activation was completed, and audit evidence was reviewed. A final check showed no active role assignment.

## Security scenario

An IAM security analyst needs temporary read-only access to identity reports without maintaining standing administrative privileges. The lab implements an eligible role assignment, requires a business justification and Azure MFA on activation, limits activation to one hour, and verifies the audit trail.

## Environment and scope

- Microsoft Entra ID P2 lab tenant: `roc`
- Dedicated cloud-only test user: Marcus Reed (`mreed`)
- Role: **Reports Reader**; tenant scope: `roc`
- Microsoft Authenticator registered for the test user
- No Global Administrator role assignment was created for this test
- This is a controlled demonstration, not evidence of a production deployment

## Implementation and verification

| Phase | Action | Evidence / result |
|---|---|---|
| 1. Discovery | Reviewed PIM navigation and role inventory | Screenshots 01–02 |
| 2. Baseline | Checked Reports Reader eligible and active assignments | Neither had results before the test; 03–04 |
| 3. Identity preparation | Created a cloud-only standard test user and verified active P2 licensing | 05–06 |
| 4. Authentication | Confirmed no usable methods, then registered Microsoft Authenticator | 07–08 |
| 5. Role security | Changed activation maximum from 8 hours to **1 hour**, selected **Azure MFA**, retained required justification; no approval requirement | 09–11 |
| 6. Eligibility | Granted Marcus Reed a time-bounded **eligible** Reports Reader assignment through Nov. 23, 2027 | 12–13 |
| 7. JIT activation | Submitted a one-hour activation with business justification | 14–15; role showed **Activated** |
| 8. Audit | Inspected PIM Resource audit | 16; activation completed, **Succeeded**, Nov. 23, 2026, 7:32:41 AM; expiry 8:32:34 AM (portal-displayed time) |
| 9. End of access | Reviewed Active assignments | 17; **No results** |

## Key security findings

1. **Eligibility is not active access.** Marcus could request the Reports Reader role without holding the role continuously.
2. **Activation controls matter.** The role's baseline permitted up to eight hours and did not explicitly require MFA on activation. The saved configuration reduced the maximum to one hour and selected Azure MFA, with justification required.
3. **PIM is auditable.** The successful activation audit record included the requestor, target role, business reason, status, and expiration time.
4. **Temporary access ended.** The final Active assignments view displayed no results. The available evidence does not establish whether this was manual deactivation or expiry.

## Evidence and limitations

[View the 17-screenshot evidence index](screenshots/README.md) · [Read the detailed case study](docs/case-study.md)

**MFA evidence limitation:** The configuration required Azure MFA, and activation succeeded. The screenshots do **not** independently demonstrate a fresh Authenticator challenge; a previously satisfied MFA claim may meet the requirement. Do not describe a fresh push notification as verified.

**Scope limitation:** The screenshots establish PIM role state and audit results, not a separate functional test of report access or application-level authorization. The role's one-year eligibility window is distinct from its one-hour activation limit.

## Skills demonstrated

Microsoft Entra ID · Privileged Identity Management · Just-in-Time (JIT) access · Least privilege · Eligible vs. active role assignments · MFA activation requirements · Business justification · PIM audit analysis · Access lifecycle verification · Security evidence documentation

## Security and privacy

All identities and role changes were performed in a lab tenant. Before publishing screenshots, redact unnecessary identifiers (especially the correlation ID in Screenshot 16), credentials, tokens and sensitive account details. No passwords or MFA enrollment QR codes belong in this repository.
