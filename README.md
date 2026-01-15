# JakubTech — Azure Tenant Baseline + Infra + Hybrid Identity (AD Connect)

## Objective
Build a secure Microsoft Entra ID tenant baseline, deploy minimal Azure infrastructure in **West Europe**, and integrate an on-prem AD DS domain using **Azure AD Connect** with controlled sync scope.

## Hard scope rules (non-negotiable)
### Cloud-only identities (exactly 3)
Only these **three** cloud-only admin accounts exist in Entra ID:
1) `bg-admin@jakubtech.co.uk` — Break-glass (emergency only)
2) `admin-id@jakubtech.co.uk` — Identity administration
3) `admin-ops@jakubtech.co.uk` — Azure operations

### All other identities
- All business users and groups are created in **on-premises Active Directory**
- They are synchronized to Entra ID using **Azure AD Connect**
- UPN naming convention for users: `firstname@jakubtech.co.uk`

## Region and sizing constraints
- Azure region: **West Europe**
- VM minimum size used in this project: **Standard_D2s_v3**

## Documentation order
1. `docs/00-scope.md`
2. `docs/01-identity-model.md`
3. `docs/02-tenant-security-baseline.md`
4. `docs/03-azure-core-infra.md`
5. `docs/04-hybrid-ad-design.md`
6. `docs/05-adconnect-deploy.md`
7. `docs/06-validation.md`
8. `docs/07-runbooks.md`

## Evidence and hygiene
- No secrets committed.
- Screenshots go under `evidence/screenshots/` (redacted).
- Every change is logged in `evidence/changelog.md`.
- This project uses the real domain `jakubtech.co.uk` in documentation.

