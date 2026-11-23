# IAM Security Case Study — PIM Just-in-Time Reports Reader Access

**Case ID:** IAM-PIM-005  
**System:** Microsoft Entra ID P2 / Privileged Identity Management  
**Test identity:** Marcus Reed (cloud-only standard user)  
**Role:** Reports Reader  
**Tenant:** roc  
**Date:** November 23, 2026

## Request and security objective

Demonstrate that a user can be made *eligible* for a limited administrative reporting role, activate it only when required, provide a documented business reason, and leave an auditable record without retaining standing active privileges.

## Baseline

The Reports Reader role initially showed no eligible or active assignments. Activation settings allowed up to eight hours, required justification, did not require approval, and displayed `None` for the activation authentication requirement. Marcus initially had no usable authentication method. See screenshots 03–04, 07 and 09.

## Controls implemented

- Assigned Marcus an active Entra ID P2 license and registered Microsoft Authenticator.
- Configured **one-hour maximum activation duration**.
- Configured **Azure MFA required on activation**.
- Retained **mandatory activation justification**.
- Kept approval and ticket-information requirements disabled for this self-service lab.
- Assigned **eligible**, time-bounded Reports Reader access, expiring November 23, 2027. Eligibility did not itself activate the role.

## Test execution and evidence

1. In Marcus's PIM **My roles**, Reports Reader appeared under **Eligible assignments** with an **Activate** action (13).
2. The activation panel showed a **one-hour duration** and a required **Reason** field (14).
3. The reason documented temporary access to review Microsoft Entra sign-in and audit reports for IAM-PIM-005.
4. After submission, Reports Reader appeared under **Active assignments** with state **Activated** and an expiration of **November 23, 2026, 8:32:34 AM** (15).
5. The **Resource audit** event `Add member to role completed (PIM activation)` reported **Succeeded**, with Marcus as requestor/subject, Reports Reader as target, the justification, and expiration. The audit timestamp displayed **November 23, 2026, 7:32:41 AM** (16).
6. A later check of **Active assignments** displayed **No results** (17).

## Outcome

**Passed:** Eligible role assignment, saved one-hour activation controls, configured Azure MFA requirement, mandatory justification, successful JIT activation, successful PIM audit record, and no active assignment in the final view.

**Not independently demonstrated:** A fresh MFA challenge; manual deactivation versus natural expiry; application-level report access; approval workflow (not enabled).

## Analyst interpretation

The lab illustrates reduced standing privilege through PIM eligibility, time-limited role elevation, and traceability. The one-year eligibility duration does **not** mean one year of active privileges. A successful activation under an MFA-required policy does not by itself establish that the user received a new MFA prompt.

## Cleanup / follow-up

If the lab is no longer needed, review whether to remove Marcus's eligible assignment and whether to restore the Reports Reader role settings to the tenant's intended baseline. Such cleanup has not been verified in the captured evidence; do not claim it was performed.
