# 02 — Tenant security baseline (admin-first)

## Outcome
Admins are protected with MFA and legacy auth is blocked tenant-wide.

## Conditional Access (minimum)
CA-001 Require MFA for admin accounts
- Users: `admin-id@jakubtech.co.uk`, `admin-ops@jakubtech.co.uk`
- Exclude: `bg-admin@jakubtech.co.uk`
- Apps: All cloud apps
- Grant: Require MFA

CA-002 Block legacy authentication
- Users: All users
- Exclude: `bg-admin@jakubtech.co.uk` (documented exception)
- Conditions: Client apps -> legacy authentication
- Grant: Block

CA-003 Admin portal restrictions (optional)
- Users: admin-id, admin-ops
- Apps: Microsoft admin portals
- Grant: Require MFA
- Session: sign-in frequency (optional)

## Other baseline settings
- Authentication methods: prefer Microsoft Authenticator
- Monitor break-glass sign-ins (alerting via logs)

## Evidence
- Screenshots for each CA policy + exclusions
- Record all exclusions in evidence/changelog.md
