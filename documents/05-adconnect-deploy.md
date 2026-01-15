# 05 — Azure AD Connect deployment

## Outcome
AD Connect syncs only the intended OUs and is monitored for failures.

## Placement
Recommended:
- Install AD Connect on a dedicated server: `VM-JT-ADCONNECT-01`
- Do not install on the Domain Controller (acceptable in a lab, not ideal)

## Pre-checks
- Time sync correct (DC and AD Connect server)
- DNS resolution to DC works
- Outbound HTTPS allowed to Microsoft endpoints
- Credentials available:
  - Entra: Global Admin (admin-id) or equivalent
  - AD: Enterprise Admin

## Configuration (project standard)
- Sign-in method: Password Hash Sync (PHS)
- OU filtering: include only `OU=JT\Users` (after initial IT-only test)
- Optional: Seamless SSO only if you plan to test it and document it

## Validation
- Test user sync appears in Entra as "On-premises sync enabled"
- Password change on-prem -> sign-in works in cloud after sync
- No persistent connector/export errors in Sync Service Manager

## Evidence
- Screenshots: OU filtering, sync status, synced user property page
- Record configuration choices in evidence/changelog.md
