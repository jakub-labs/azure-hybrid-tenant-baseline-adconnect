# Azure Tenant Baseline + Minimal Infra + Hybrid Identity (AD Connect)

## Purpose
Build a secure Entra ID tenant baseline, deploy minimal Azure infrastructure, and integrate an on-prem AD domain using Azure AD Connect.

## Key constraint (scope)
### Cloud-only objects
- Exactly **3 cloud admin accounts** exist in Entra ID:
  1) `bg-admin@userx.co.uk` (break-glass)
  2) `admin-id@userx.co.uk` (identity admin)
  3) `admin-ops@userx.co.uk` (Azure ops admin)

### Everything else
- All business users and groups are created **on-premises AD** and **synced** to Entra ID via **Azure AD Connect**.
- No cloud-only user sprawl.

## Build order
1. docs/00-scope-and-assumptions.md
2. docs/01-cloud-admin-accounts.md
3. docs/02-tenant-security-baseline.md
4. docs/03-azure-core-infra-minimal.md
5. docs/04-hybrid-ad-and-ou-design.md
6. docs/05-adconnect-install-and-config.md
7. docs/06-validation-and-handover.md
8. docs/07-operations-runbooks.md

## Evidence and hygiene
- No secrets committed.
- Screenshots go under `evidence/screenshots/` (redacted).
- Every change is logged in `evidence/changelog.md`.
- Use `userx` placeholders for usernames/domains in shared examples.
