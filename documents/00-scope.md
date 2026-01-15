# 00 — Scope

## In scope
- Entra ID tenant baseline security (admin protection focused)
- Azure minimal core infra in West Europe (networking, logging, minimal compute)
- Hybrid identity via Azure AD Connect with strict OU filtering
- Validation tests + operational runbooks

## Out of scope
- Intune compliance/device posture enforcement (optional later)
- Complex landing zone patterns (multi-sub, hub/spoke, private endpoints everywhere)
- Full SIEM/Sentinel content engineering

## Constraints
- Exactly 3 cloud-only admin accounts: `bg-admin`, `admin-id`, `admin-ops`
- All other users/groups created on-prem and synced
- User UPN pattern: `firstname@jakubtech.co.uk`
- Azure region: West Europe
- VM baseline size: Standard_D2s_v3
